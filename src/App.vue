<script setup>
  import axios from "axios";
  import {ref, onMounted} from 'vue';
  const tasks = ref([]);
  const users = ref([]);

  onMounted(() =>{
    axios.get("http://localhost:3000/todos")
    .then(response => {
      console.log(response.data);
      tasks.value = response.data;
    })    

    axios.get("http://localhost:3000/users")
    .then(response => {
      console.log(response.data);
      users.value = response.data;
    })   
  });
</script>

<template>
<h1 class="text-center">Feladatok</h1>
<div v-for="task in tasks">
  {{ task.task }}
</div>
<hr>
<div v-for="user in users">
  {{ user.name }}
</div>
</template>

