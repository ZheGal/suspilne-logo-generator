<template>
  <div class="logo">
    <div class="logo_inner">
      <div class="logo_round">
        <img
          :src="imageUrl"
          v-if="imageUrl"
          class="object-cover h-full w-full"
        />
      </div>
      <div class="logo_text">
        <div v-if="firstLine">{{ firstLine }}</div>
        <div v-if="secondLine">{{ secondLine }}</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  firstLine?: string;
  secondLine?: string;
  roundColor?: string;
  imageUrl?: string;
}>();
</script>

<style lang="css" scoped>
.logo {
  @apply flex items-center justify-center;
  @apply font-['Inerta-Bold'] font-black py-12 px-2;
  @apply rounded-xl border bg-slate-700 text-white uppercase;
  @apply pointer-events-none select-none;
}

.logo_inner {
  @apply flex flex-row items-center justify-center gap-[30px];
  @apply max-sm:scale-50;
}

.logo_round {
  @apply aspect-[1/2] min-w-[60px] max-w-[60px] bg-[v-bind(roundColor)] rounded-l-full overflow-hidden;
}

.logo_text {
  @apply flex flex-col leading-[54px] font-bold text-white text-[52px];
}
</style>
