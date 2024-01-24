<template>
  <FormComponent />
  <ButtonComponent 
    :nombre="nombreButton" 
    :disabledButton="true" 
    clase="success" />
  <ButtonComponent 
    buttonType="submit" 
    nombre="Eliminar" 
    :disabledButton="false" 
    clase="danger" />
  <ButtonComponent nombre="OK" />
  <ButtonComponent nombre="ADVERTENCIA" clase="warning" />
  <br />
  <br />
  <br />
  <ReactiveFormComponent />
  <br />
  <br />
  <br />
  <CardNoticiaComponent
    v-for="noticia in noticiaList"
    :key="noticia.id"
    :id="noticia.id"
    :title="noticia.title" 
    :body="noticia.body"
    @accionEliminar="eliminarNoticia(noticia.id)"/>
</template>

<script setup lang="ts">
import { ref } from "vue";
import ButtonComponent from "./components/ButtonComponent.vue";
import CardNoticiaComponent from "./components/CardNoticiaComponent.vue";
import FormComponent from "./components/FormComponent.vue";
import ReactiveFormComponent from "./components/ReactiveFormComponent.vue";

const nombreButton = "Enviar";

export interface INoticia {
  id: number;
  title: string;
  body: string;  
}

const noticiaList = ref<INoticia[]>([
  { id: 1, title: "Nueva especie", body: "Se decubre nueva especia de perro en África" },
  { id: 2, title: "Robótica en la era digital", body: "Se construyen robots con IA" },
  { id: 3, title: "Nacimiento de Juan López", body: "Nace niño en el desierto del Sahara" },
  { id: 4, title: "Descubrimiento de tesoro", body: "Se haya un tesoro enterrado en Argentina" }
]);

const eliminarNoticia = (id: number) => {
  noticiaList.value = noticiaList.value.filter(noticia => noticia.id != id);
}
</script>
