<script setup>
import { ref } from 'vue'
const show = ref(true)

const ismlar = ['ali', 'vali', 'hasan', 'husan']
const active = ref(false)
</script>

<template>
  <h1>Start Foundation</h1>
  <div>
    <button @click="show = !show">Bos</button>
    <p v-if="show">men korinib turpman</p>
    <p v-else>men yashirinman</p>
  </div>
  <div>
    <ul>
      <li v-for="(ism, index) in ismlar" :key="index">
        {{ ism }}
      </li>
    </ul>
  </div>
  <div>
    <button @click="active = !active" :class="{active: active}">Bos</button>
  </div>
</template>
<style scoped>
.active {
  background-color: green;
  color: white;
}
</style>