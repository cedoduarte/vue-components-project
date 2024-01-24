<template>
    <button 
        :type="buttonType" 
        :class="asignaClase" 
        :disabled="disabledButton">
            {{ nombreUpperCase() }}
    </button>
</template>

<script setup lang="ts">
import {defineProps,computed} from "vue";

type TIPO_BOTON = "button" | "submit" | "reset";
type TIPO_CLASE = "success" | "danger" | "primary" | "warning";

//defineProps(["nombre", "disabledButton", "buttonType"]);
const props = defineProps({
    nombre: {
        type: String,
        required: true
    },
    disabledButton: {
        type: Boolean,
        default: false
    },
    buttonType: {
        type: String as () => TIPO_BOTON,
        default: "button",
        validator(value: string) {
            return ["button","submit","reset"].includes(value);
        }
    },
    clase: {
        type: String as () => TIPO_CLASE,
        default: "primary"      
    }
});

const asignaClase = computed(() => {
    return `btn btn-${props.clase}`;
});

const nombreUpperCase = () => {
    return props.nombre.toUpperCase();
}
</script>