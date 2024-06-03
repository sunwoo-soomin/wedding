<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="">
      <RouterLink to="/card"></RouterLink>
    </div>
  </header>
  <RouterView />
</template>
