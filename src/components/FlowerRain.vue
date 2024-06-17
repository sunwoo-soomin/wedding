<script setup lang="ts">
import FlowerLeaf from "../components/FlowerLeaf.vue";

</script>

<template>
  <div>
    <FlowerLeaf v-for="n in 10" :key="`leaf-${n}`" />
  </div>
</template>