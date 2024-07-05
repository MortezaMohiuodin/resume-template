<template>
  <div class="bg-black">
    <div class="max-w-[1200px] mx-auto">
      <div class="flex justify-center items-center bg-custom pt-[130px]">
        <div class="w-[850px] h-[1100px] rounded-md">
          <slot />
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts"></script>
<style scoped>
.bg-custom {
  background: linear-gradient(110deg, #b3ced0 60%, #e2e2e2 60%);
}
</style>
