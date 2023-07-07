<template>
  <div>
    <header>
            <span>To</span>
            <img src="../../img/1057053.png">
            <span>Do</span>
    </header>
    <div class="todoapp">
      <div class="data">
        {{ today }}
      </div>
        <ul>
          <li v-for="todo in todos" :key="todo">{{ todo }}</li>
        </ul>
      <div class="textarea">
        <input type="text" v-model="newEl" @keydown="onKeydown">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      today: new Date().toLocaleDateString(),
      todos: [
        'sleep'
      ],
      newEl: ''
    }
  },
  methods: {
    addTodo() {
      return this.todos.push(this.newEl)
    },
    onKeydown(e) {
      if (e.keyCode === 13) {
          this.addTodo();
          this.newEl = '';
        }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@font-face {
  font-family: BacasimeAntique;
  src: url(../../fonts/BacasimeAntique-Regular.ttf);
}
  .todoapp {
    margin: 2rem auto;
    background-color: rgba(54, 189, 235, .1);
    max-width: 450px;
    min-height: 500px;
    border: 3px dotted rgb(236, 74, 184);
    position: relative;
  }
  img {
  width: 5rem;
  height: 5rem;
}
header{
  margin: 0 auto;
  max-width: 450px;
  display: flex;
  justify-content: center;
  align-items: center;
}
span {
  font-family: BacasimeAntique;
  color: blueviolet;
  font-size: 4rem;
  padding: 0 2rem;
}
.data {
  font-family: BacasimeAntique;
  color: blueviolet;
  font-size: 3rem;
  border-bottom: .1rem solid rgb(236, 74, 184);
  padding: 1rem 0;
}
input{
  min-width: 98%;
  height: 41px;
  position: absolute;
  bottom: 0;
  left: 1px;
  font-family: BacasimeAntique;
  font-size: 40px;
}
li {
  font-family: BacasimeAntique;
  color: rgb(163, 5, 242);
  font-size: 34px;
  list-style-type: '\2714';
}
</style>
