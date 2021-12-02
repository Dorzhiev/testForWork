<template>
    <div>
        <h1>Todos</h1>
    <ul>
      <li v-for="todo of todos" :key="todo.authorName">
        {{ todo.date }}{{ todo.authorName }} {{ todo.authorUrl }} 
         <div class="text tone"> {{ todo.content }} </div>
      </li>
    </ul>
    </div>
</template>

<script>
import axios from "axios";
    export default {
        name: "TodoList",
        data() {
            return {
                todos: [],
                
            }
        },
        async created() {
            try {
                const res = await axios.get(`http://localhost:3001/todos`);
                this.todos = res.data;
            } catch (e) {
                console.error(e)
            }
        }
        
    }
</script>

<style scoped>
h1 {
  text-decoration: underline;
}

li {
  color: rgb(5, 5, 5);
}
.tone {
    background: linear-gradient(45deg, red,yellow, green);
}
</style>