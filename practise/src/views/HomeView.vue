<script setup>
import { ref } from 'vue'

const active = ref(false)
const show = ref(false)
const ism = ref("Ali")
const time = ref(false)

const son = ref(10)
let intervalId = null


const user = ref([
  {
    id: 1,
    ism: 'Ali',
    yosh: 20,
    rasm: 'https://images.uzum.uz/crokh56vip07shn5qbf0/t_product_540_high.jpg',
    narx: 10000,
    soni: 2
  },
  {
    id: 2,
    ism: 'salim',
    yosh: 25,
    rasm: 'https://images.uzum.uz/crokh56vip07shn5qbf0/t_product_540_high.jpg',
    narx: 12000,
    soni: 2
  }
])

const start = () => {
  if (intervalId) return

  intervalId = setInterval(() => {
    son.value--
  }, 1000)
}
const stop = () => {
  clearInterval(intervalId)
  intervalId = null
}

const start1 = () => {
  setTimeout(() => {
    time.value = true
  }, 2000)
}

</script>

<template>


  <div class="vaqt">
    <p>{{ son }}</p>
    <button @click="start">start</button>
    <button @click="stop">stop</button>
  </div>

  <button @click="start1">time</button>

  <p v-if="time">2 second</p>
  <p @click="ism = 'Vali'">{{ ism }}</p>

  <button @click="show = !show">Show/Hide</button>
  <p v-if="show">laylo</p>

  <button @click="active = !active">Bos</button>

  <transition name="fade">

  </transition>


  <h1>salom</h1>
  <div v-for="user in user" :key="user.id">
    <img :src="user.rasm" width="120" />
    <p>ID: {{ user.id }}</p>
    <p>ISM: {{ user.ism }}</p>
    <p>YOSH: {{ user.yosh }}</p>
  </div>
</template>


<style scoped>
.vaqt {
  width: 300px;
  height: 300px;
  border: 1px solid green;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.box {
  width: 200px;
  height: 200px;
  background-color: red;
}

.move {
  transform: translateX(150px) rotate(45deg);
}
</style>