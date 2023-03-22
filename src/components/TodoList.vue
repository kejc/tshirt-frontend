<script setup>
import { ref } from 'vue';
import ListItem from './ListItem.vue';

const todos = ref([
  {
    title: 'Gin',
    done: false,
  },
  {
    title: 'Lemon',
    done: false,
  },
  {
    title: 'Tonic',
    done: true,
  },
]);
const preLoader = ref(false);
const error = ref(null);

/*
fetch('https://jsonplaceholder.typicode.com/todos')
  .then((response) => {
    return response.json();
  })
  .then((response) => {
    console.log(response);
    todos.value = response;
  })
  .catch((err) => {
    console.log(err);
    error.value = err;
  })
  .finally(() => {
    preLoader.value = false;
  });
*/

console.log(todos);
</script>

<template>
  <div v-if="preLoader" class="preLoader">
    <h1>Loader</h1>
  </div>

  <div v-if="error">
    Der var en fejl i at hente listen
  </div>

  <ul>
    <ListItem v-for="todo in todos" :data="todo" />
  </ul>
</template>

<style>
.preLoader {
  background: #ff1493;
  bottom: 0;
  left: 0;
  position: fixed;
  right: 0;
  top: 0;
}

.preLoader h1 {
  left: 50%;
  position: absolute;
  top: 50%;
  transform: translate(-50%, -50%);
}
</style>
