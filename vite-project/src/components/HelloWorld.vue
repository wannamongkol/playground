<script setup lang="ts">
import { reactive, ref } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0)
const isDisabled = ref(true)
const msgBox = ref()
const obj1 = reactive({
  test : "reactive"
})


const switchBtn = () => {
  isDisabled.value = !isDisabled.value; 
}
</script>

<template>
  <h1>{{ msg }}</h1>
  <h2>{{ obj1.test }}</h2>

  <div class="card">
    <button type="button" @click="count++" :disabled="isDisabled">count is {{ count }}</button>

    <button @click="switchBtn">switch</button>
 
  </div>

  <div class="container p-4">
    <h5>Text Container : {{ msgBox }}</h5>
    <input v-model="msgBox" placeholder="testing">

  </div>


</template>

<style scoped>



</style>
