<template>
  <div class="container mx-auto py-4">
    <h1 class="text-center text-xl mb-4 font-black">
      Генератор логотипів "Суспільного"
    </h1>
    <div class="main-form">
      <label class="main-label">
        <div class="text-right w-[120px]">Перший рядок:</div>
        <input type="text" v-model="firstLine" class="main-input" />
      </label>
      <label class="main-label">
        <div class="text-right w-[120px]">Другий рядок:</div>
        <input type="text" v-model="secondLine" class="main-input" />
      </label>
      <label class="main-label">
        <div class="text-right w-[120px]">Колір:</div>
        <input type="color" v-model="color" />
      </label>
    </div>
    <hr class="my-4 border-black/30" />
    <Logo :firstLine="firstLine" :secondLine="secondLine" :roundColor="color" />
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Logo from "./components/Logo.vue";

const firstLine = ref<string>("Суспільне");
const secondLine = ref<string>("Новини");
const color = ref<string>("#FBED21");
</script>

<style lang="css" scoped>
.main-form {
  @apply flex flex-col gap-1 container max-w-[350px] mx-auto;
}
.main-label {
  @apply flex flex-row gap-4 w-full;
}
.main-input {
  @apply border border-black px-1 flex-1 rounded-md;
}
</style>
