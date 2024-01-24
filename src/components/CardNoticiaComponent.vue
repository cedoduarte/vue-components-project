<template>
    <div class="card-noticia card">
        <div class="card-body">
            <h5 class="card-title">
                {{ title }}
            </h5>
            <p class="card-text">
                {{ body }}
            </p>
        </div>
        <div class="card-footer">
            <ButtonComponent nombre="Eliminar" 
                             clase="danger"
                             @click="emit('accionEliminar')" />
        </div>
    </div>
</template>

<script setup lang="ts">
import { defineProps, defineEmits } from "vue";
import ButtonComponent from "./ButtonComponent.vue";

const emit = defineEmits(["accionEliminar"]);

defineProps({
    id: {
        type: Number,
        required: true
    },
    title: {
        type: String,
        required: true
    },
    body: {
        type: String,
        required: true
    }
});
</script>

<style scoped>
.card-noticia {
    margin: 10px;
}
</style>