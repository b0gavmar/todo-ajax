<script setup>
  import axios from "axios";
  import {ref, onMounted} from 'vue';

  onMounted(() =>{
    axios.get("http://localhost:3000/todos")
    .then(response => console.log(response))    
  })
</script>

<template>
<h1 class="text-center">Feladatok</h1>
</template>

