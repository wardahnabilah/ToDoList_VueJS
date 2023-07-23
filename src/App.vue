<script setup>
  import { ref } from 'vue';
  import TodoItem from './components/TodoItem.vue'

  const today = new Date()
  const day = today.getDate() > 10 ? today.getDate() : '0' + today.getDate()
  const month = today.getMonth() > 10 ? today.getMonth() : '0' + today.getMonth()
  const year = today.getFullYear()
  const hours = today.getHours() > 10 ? today.getHours() : '0' + today.getHours()
  const minutes = today.getMinutes() > 10 ? today.getMinutes() : '0' + today.getMinutes()

  const deadline = ref(`${year}-${month}-${day}`)
  const time = ref(`${hours}:${minutes}`)
  
</script>

<template>
  <div class="container mx-auto">
    <h1 class="text-center text-3xl font-bold text-white mb-5">Todo List</h1>
    <div class="grid max-w-[90%] md:max-w-[25%] mx-auto mb-12">
      <input class="px-5 py-2 mb-3 bg-transparent border outline-none focus:border-[#4d71d3] rounded-full text-white" type="text" placeholder="What to do...">
      <label class="mb-2 block text-white" for="deadline">Deadline: </label>
      <div class="flex mb-6 ">
        <input class="px-5 py-1.5 mr-auto bg-transparent text-white bg-none border outline-none focus:border-[#4d71d3] rounded-full" type="date" v-model="deadline" id="deadline">
        <input class="px-5 py-1.5 bg-transparent text-white border outline-none focus:border-[#4d71d3] rounded-full" type="time" v-model="time">
      </div>
      <button class="p-1.5 bg-[#e9445f] hover:bg-[#8b2738] shadow rounded-full text-white font-bold">ADD</button>
    </div>
    <TodoItem />  
  </div>

  
</template>