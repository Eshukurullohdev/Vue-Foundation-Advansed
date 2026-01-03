<script setup>
import { reactive, ref, computed } from 'vue'
const show = ref(true)

const ismlar = ['ali', 'vali', 'hasan', 'husan']
const active = ref(false)
const son = ref(0)
const user = reactive({
  ism: "John",
  yosh: 25
})
const list = reactive([
  "Olma",
  "Banan"
])

const kopaytir = () => {
  console.log("Bosildi");
  
}

const ota = () => alert('Ota bosildi')
const bola = () => alert('bola bosildi')
const text = ref('')


const double = ref(0)

const ikkiBarovar = computed(() => {
  return son.value * 2
})
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
  <div>
    <button @click="son++">+</button>
    <button @click="son--">-</button>
    <p>{{ son }}</p>
  </div>
  <div>
    <p>{{ user.ism }}</p>
    <p>{{ user.yosh }}</p>
  </div>
  <div>
    <button @click="list.push('Anor')">Qosh</button>

    <ul>
      <li v-for="item in list" :key="item">{{ item }}</li>
    </ul>
  </div>

  <div>
    <button @click="kopaytir">2x</button>
    <input type="text" @input="text = $event.target.value">
    <p>{{ text }}</p>
  </div>
  <div @click="ota">
      <button @click.stop="bola">Bos</button>
  </div>
  <div>
    <input v-model="son">
    <p>2 barobar: {{ ikkiBarovar }}</p>
  </div>
  <div>
    <RouterLink to="/just">Just Componentga o'tish</RouterLink>
  </div>
  
</template>
<style scoped>
.active {
  background-color: green;
  color: white;
}
</style>