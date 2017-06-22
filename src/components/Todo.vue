<template>
  <div class="todo">
    <h1>{{ msg }}</h1>
    <img src="https://i.stack.imgur.com/TqZyS.jpg">
    <!-- input and list -->
    <input v-model="newTodo" v-on:keyup.enter="submit">
    <ul id="example-1">
      <todoitem v-for="item in arr"></todoitem>
    </ul>
    <!-- end input & list -->
  </div>  
</template>

<script>
import TodoItem from './TodoItem'
export default {
  name: 'todo',
  components: {
    TodoItem
  },
  data () {
    return {
      msg: 'What Do You Have To Do Today?',
      arr: [
      { message: 'Foo' },
      { message: 'Bar' }
      ],
      newTodo: ''
    }
  },
  methods: {
    submit: function () {
      this.arr.push({message: this.newTodo})
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
img {
  width:10%;
}
ul {
  text-align:center;
  width:30%;
  margin: 0 auto;
}
</style>
