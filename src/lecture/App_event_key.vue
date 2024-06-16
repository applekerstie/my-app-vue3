<template>
  <div>
    <input type="text" @keyup="addTodo1" />
    <ul>
      <li v-for="(todo, idx) in todos1" :key="idx">
        {{ todo }}
      </li>
    </ul>
  </div>

  <hr />
  <div>
    <input type="text" @keyup.enter="addTodo2" />
    <ul>
      <li v-for="(todo, idx) in todos2" :key="idx">
        {{ todo }}
      </li>
    </ul>
  </div>
</template>

<script>
import { reactive } from 'vue';

export default {
  setup () {
    const todos1 = reactive([]);

    const addTodo1 = (event) => {
      //console.log( event.key );
      if( event.key === 'Enter') {
        todos1.push( event.target.value );
      }
    }

    const todos2 = reactive([]);
    const addTodo2 = (e) => {
      todos2.push( e.target.value );
      e.target.value = '';
      e.target.focus();
    }

    return {
      todos1,
      addTodo1,
      todos2,
      addTodo2,
    }
  }
}
</script>

<style scoped>

</style>