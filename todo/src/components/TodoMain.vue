<template>
  <div>
    <h1>TODO LIST</h1>
    <input class="inputBox" type="text" placeholder="할일을 입력하세요." v-model="todoItem" @keyup.enter="addTodo">
    <button v-on:click="addTodo">등록</button>
    <div>
      <ul>
        <li v-for="list in todoList" :key="list">{{list}}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      todoItem: '',
      todoList: []
    }
  },
  methods: {
    addTodo: function () {
      if (this.todoItem !== '') {
        this.todoList.includes(this.todoItem) ? alert('이미 추가된 할일입니다.') : this.todoList.push(this.todoItem)
        this.todoItem = ''
      } else {
        alert('할일을 입력해주세요')
      }
    },
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body {
  text-align: center;
  background-color: #f6f6f8;
  width: 100%;
}

input:focus {
  outline: none;
}
</style>
