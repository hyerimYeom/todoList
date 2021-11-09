
<template>
  <div>
    <div>To-Do list</div>
    <div id="table">
        <div class="row">
            <span class="cell col1">작성자</span>
            <span class="cell col2">내용 </span>
            <span class="cell col3">마감일</span>
            <span class="cell col4">done</span>
        </div>
        <!-- <div class="row" > --> 
            <TodoList :todo = "todo" v-for="(todo, idx) in todolist" :key="idx" />
        <!-- </div>   -->
    </div>
  </div>
</template>

<script>
import TodoList from "./components/TodoList.vue";
import todolist from "./assets/todolist_sample.js";

export default {
  name: "App",
  data() {
    return {
      todolist: todolist,
    };
  },
  components: {
      TodoList
  },
};
</script>
