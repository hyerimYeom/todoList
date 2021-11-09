<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div>
    <div>To-Do list</div>
    <!-- 표 연습 -->
   <div id="table">
    <div class="row">
    <span class="cell col1">작성자</span>
    <span class="cell col2">내용 </span>
    <span class="cell col3">마감일</span>
    <span class="cell col4">done</span>
    </div>
    <div class="row"> 
    <span class="cell col1"> {{todolist[0].user}} </span>
    <span class="cell col2"> todo list 프로젝트 오늘 완성하기</span>
    <span class="cell col3"> 2021-11-09</span>
    <span class="cell col4"> 아이콘 필요 </span>
    </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import todolist from './assets/todolist_sample.js'

export default {
  name: 'App',
  data() {
    return {
      todolist : todolist
    }
  },
  components: {
    // HelloWorld
  }
}
</script>

<style>
#table {display: table; width: 100%;}
.row {display: table-row;}
.cell {display: table-cell; padding: 3px; border-bottom: 1px solid #DDD;}
.col1 {width: 20%;}
.col2 {width: 20%;}
.col3 {width: 40%;}
.col4 {width: 20%;}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
