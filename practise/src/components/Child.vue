<template>
  <div>
    <p style="color: black;">Ism: {{ ism }}</p>
    <p>Yosh: {{ yosh }}</p>
  </div>
</template>

<script setup>
defineProps({
  ism: String,
  yosh: Number
})
</script>
