
<template>
  <div>
    <div>To-Do list</div>
    <!-- 입력창 -->
    <div style="display:flex; flex-direction:row; justify-content:center; align-items:stretch; column-width:100%;">
      <input style="width:80%" class="item" type="text" name="" id="" value="" placeholder="오늘은 어떤 일이 날 기다리고 있나?"/>
      <button class="item">입력</button>
    </div>
    <div id="table">
        <div class="row text-bold">
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
<style>
.item{

  flex-grow: 1;
  /* column-fill : auto; */

}
</style>
