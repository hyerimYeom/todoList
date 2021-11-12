
<template>
  <div>
    <div>To-Do list</div>
    <!-- 입력창 -->
    <div style="display:flex; flex-direction:row; justify-content:center; align-items:stretch; column-width:100%;">
      <input style="width:70%" class="item" type="text" v-model="newTodo.title" placeholder="오늘은 어떤 일이 날 기다리고 있나?"/>
      <input style="width:10%" class="item" type="date" v-model="newTodo.endDate" />
      <button class="item" @click="addTodo()">입력</button>
    </div>
    <div id="table">
        <div class="row text-bold">
            <span class="cell col1"> 작성자 </span>
            <span class="cell col2"> 내용 </span>
            <span class="cell col3"> 마감일 </span>
            <span class="cell col4"> DONE </span>
            <span class="cell col5"> </span>
        </div>
        <!-- <div class="row" > --> 
          <List 
            :todo = "todo" 
            v-for="(todo, idx) in todolist" 
            :key="idx" 
            @todo-list = "todoList(idx)"
            @update = "update(idx, $event)"
            /> 
        <!-- </div>   -->
    </div>
  </div>
</template>

<script>
import List from "./components/TodoList.vue";
import todolist from "./assets/todolist_sample.js";

export default {
  name: "App",
  data() {
    return {
      title:'',
      todolist: [...todolist], //원래 todolist
      originalTodo : {} ,
      newTodo : {
        id: todolist.length,
        user : 'HR',
        title :'',
        startDate : '',
        endDate:'',
        done : false
        }, //push할 새로운 todolist
    };
  },
  methods: {
  update : function(id, params){
      //기존 데이터 저장
    this.originalTodo = {...todolist[id]};
    console.log(params)
    
  },
   todoList: function(id){
       this.todolist[id].done = !this.todolist[id].done
    },
    appendLeadingZeroes : function(n){
        if(n <= 9){
          return "0" + n;
        }
        return n
    },
    addTodo:function(){ 
      //누를때 들어가야해서,
      let current_datetime = new Date()

      let formatted_date = current_datetime.getFullYear() + "-" + this.appendLeadingZeroes(current_datetime.getMonth() + 1) + "-" + this.appendLeadingZeroes(current_datetime.getDate()) + " " + this.appendLeadingZeroes(current_datetime.getHours()) + ":" + this.appendLeadingZeroes(current_datetime.getMinutes()) + ":" + this.appendLeadingZeroes(current_datetime.getSeconds())

      this.newTodo.startDate = formatted_date;
      this.todolist.push({...this.newTodo});
      
    },
  },
  components: {
      List
  },
};
</script>
<style>
.item{

  flex-grow: 1;
  /* column-fill : auto; */

}
</style>
