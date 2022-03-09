<template>
  <div id="app">
    <input
      placeholder="Enter TODO item"
      type="text"
      class="input__lg"
    />
    <button class="btn btn__primary btn__lg">Add</button>
    
    <span>1 out of 2 tasks completed</span>
    
    <div aria-labelledby="list-summary" class="stack-large">
      <to-do-item class="todo-item__container" v-for="item in toDoItems" :key="item.id"
        :description="item.description" 
        :status="item.status" 
        :id="item.id">
      </to-do-item>
  
    </div>
  </div>
</template>

<script>
import ToDoItem from './components/ToDoItem';
// eslint-disable-next-line
import http from "@/http-commons";

export default {
  name: 'app',
  components: {
    ToDoItem,
  },
  data() {
    return {
      toDoItems: []
    };
  },
  mounted() {
      http.get("/todos").then(val => {
        this.toDoItems = val.data;
        });
    }
};
</script>

<style>
/* Global styles */
.btn {
  padding: 0.8rem 1rem 0.7rem;
  border: 0.2rem solid #4d4d4d;
  cursor: pointer;
  text-transform: capitalize;
}
.btn__danger {
  color: #fff;
  background-color: #ca3c3c;
  border-color: #bd2130;
}
.btn__filter {
  border-color: lightgrey;
}
.btn__danger:focus {
  outline-color: #c82333;
}
.btn__primary {
  color: #fff;
  background-color: #1f551f;
}

.btn__secondary {
  color: #fff;
  background-color: #a8a61f;
}
.btn-group {
  display: flex;
  justify-content: space-between;
}
.btn-group > * {
  flex: 1 1 auto;
}
.btn-group > * + * {
  margin-left: 0.8rem;
}

[class*="__lg"] {
  display: inline-block;
  width: 100%;
  font-size: 1.9rem;
}
[class*="__lg"]:not(:last-child) {
  margin-bottom: 1rem;
}

[class*="stack"] > * {
  margin-top: 0;
  margin-bottom: 0;
}
.stack-small > * + * {
  margin-top: 1.25rem;
}
.stack-large > * + * {
  margin-top: 2.5rem;
}

#app {
  background: #fff;
  margin: 2rem 0 4rem 0;
  padding: 1rem;
  padding-top: 0;
  position: relative;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2), 0 2.5rem 5rem 0 rgba(0, 0, 0, 0.1);
}
#app h1 {
  display: block;
  min-width: 100%;
  width: 100%;
  text-align: center;
  margin: 0;
  margin-bottom: 1rem;
}

.todo-item__container {
  margin: 10px;
  border: 2px solid;
  padding: 20px;
}
</style>
