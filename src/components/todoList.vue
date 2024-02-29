<template>
 <div>{{ props.title }}</div>
 <div>{{ props.store }}</div>
 <div class="todo_list_container">

  <div class="list_lable">
   List of ToDo:
  </div>
  <ul class="todo" v-if="props.store && props.store.length">
   <!--  -->
   <li class="todo_inner" v-for="(todo, index) in props.store" :key="index">
    <div class="remove_button" @click="removeTodo(index)">
     <span>{{ todo }}</span>
     <span>
      &#x2716;
     </span>
    </div>
   </li>
  </ul>
 </div>
</template>

<script setup>
const props = defineProps(['title', 'store'])



function removeTodo(index) {
 console.log(index);
 index.splice(index, 1)
 // todoList.value.splice(index, 1);
 localStorage.setItem('todoData', JSON.stringify(props.value))
}
</script>