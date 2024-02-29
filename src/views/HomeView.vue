<template>
  <div>
    <div class="main">
      <div class="container">
        <div class="heading">
          ToDo App
        </div>
        <!--  -->
        <div class="add_todo_container">
          <div class="todo_label">Add ToDo</div>
          <div class="add_todo">
            <input type="text" class="" v-model="newTodoText" placeholder="Add ToDo" />
          </div>
          <button @click="addTodo()">Add New ToDo</button>
        </div>
        <!--  -->
        <!--  -->
        <!--  -->
        <!--  -->
        <!--  -->
        <ListTodo 
          :title='newTodoText'
          :store='todoList'
        />
        <!--  -->
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import ListTodo from './../components/todoList.vue'
const todoList = ref(JSON.parse(localStorage.getItem('todoData')) || [])
const newTodoText = ref('')

function addTodo() {
  todoList.value.push(newTodoText.value);
  console.dir(newTodoText.value);
  newTodoText.value = '';
  localStorage.setItem('todoData', JSON.stringify(todoList.value))
}


</script>

<style lang="scss">
.container {
  width: 80%;
  margin: 0 auto;
}

.heading {
  padding: 1em;
  font-size: 2vw;
}

.add {
  &_todo {
    &_container {
      padding: 10px;
      display: inline-flex;
      flex-direction: column;
      gap: 1em;
      border: 1px solid #c1c1c1;
    }
  }

}
.list{
  &_lable{
      padding-top: 10px;
    }
  }

.todo {
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 10px;
  padding-top: 10px;

  &_inner {
    display: flex;
    border: 1px solid #c1c1c1;
    width: 25vw;
    padding: 1em;
    border-radius: 10px;
    justify-content: space-between;
  }
}


.remove {

  &_button {
    cursor: pointer;
  }
}
</style>