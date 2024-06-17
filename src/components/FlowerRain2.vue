<script setup lang="ts">

import FlowerLeaf from "../components/FlowerLeaf2.vue";

</script>
<template>
  <div>
    <FlowerLeaf v-for="n in 12" :key="`leaf-${n}`" />
  </div>
</template>