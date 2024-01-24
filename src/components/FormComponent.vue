<template>
    <div>
        <h1>Formulario</h1>
        <input type="text" v-model="nombre" />
        <input type="number" v-model="edad">
        <input type="datetime-local" v-model="fecha">
    </div>
    <p>{{ nombre }} / {{ edad }} / {{ fecha }}</p>
    <div>
        <input v-model="aceptar" id="terminos" type="checkbox" />
        <label for="terminos">Acepta los términos y condiciones</label>
    </div>
    <pre>{{ aceptar }}</pre>
    <div v-if="aceptar">
        <div>
            <input type="checkbox" v-model="lenguajes" id="python" value="Python"/>
            <label for="python">Python</label>
        </div>
        <div>
            <input type="checkbox" v-model="lenguajes" id="java" value="Java">
            <label for="java">Java</label>
        </div>
        <div>
            <input type="checkbox" v-model="lenguajes" id="csharp" value="C#">
            <label for="csharp">C#</label>
        </div>
        <div>
            <input type="checkbox" v-model="lenguajes" id="clang" value="C">
            <label for="clang">C</label>
        </div>
        <div>
            <input type="checkbox" v-model="lenguajes" id="cplusplus" value="C++">
            <label for="cplusplus">C++</label>
        </div>
        <div>
            <input type="checkbox" v-model="lenguajes" id="phplang" value="PHP">
            <label for="phplang">PHP</label>
        </div>
        {{ lenguajes }}
    </div>
    <div>
        <select v-model="selectedCountry" name="pais" id="pais">
            <option disabled>Seleccione un país</option>
            <option :value="pais" v-for="(pais, index) in opciones" :key="index">
                {{ pais }}
            </option>
        </select>
        <span>{{ selectedCountry }}</span>
    </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const nombre = ref<string>("");
const edad = ref<number>(0);
const fecha = ref<string>("");
const aceptar = ref<boolean>(false);
const lenguajes = ref<string[]>(["Java"]);
const opciones = ref<string[]>(["Ecuador","Chile","México","España","Costa Rica","Perú"]);
const selectedCountry = ref<string>("México");
</script>