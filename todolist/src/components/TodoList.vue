<template>
   <div class="row">
        <span class="cell col1"> {{ todo.user }} </span>
        <div class="cell col2"  @click="show"> 
            <span> {{ todo.title }} </span>
            <div v-show="state_upate">
                <input type="text" v-model="title">
                <button @click="update(title)">확인</button>
            </div>
        </div>
        <span class="cell col3" @click="$emit('update', todo.endDate)"> {{ todoEndDate }} </span>
        <span class="cell col4 cursor-ture" @click="$emit('todo-list')"> {{ todoDone }}  </span>
        <span class="cell col5 cursor-ture" @click="$emit('delete-list')"><p>x</p></span>
    </div>
</template>

<script>
export default {
    name : 'List',
    data() {
        return {
            state_upate : false,
            title : '',
        }
    },
    props : { 
        todo : Object,  
    },
    methods : {
        show : function(){
            this.state_upate = true 
        },
        hide : function(){
            this.state_upate = false 
        },
        showToggle : function(){
            // return this.state_upate == 1 ? 0 : 1
            this.state_upate = !this.state_upate 
        },
        update : function(element){
            this.$emit('update', element)
            this.title = '' //초기화
            // this.showToggle()
            //  this.$emit('update', {element, done : () =>{
            //  }})
            //  console.log('result', result)

        }
        // checkTodo: function(){
        //     this.todo.done = !this.todo.done; 
        // }
    },
    computed : { 
        todoEndDate: function(){
            return this.todo.endDate.slice(0,10)
        },
        todoDone : function(){
            return this.todo.done === false ? 'X' : 'O'
        }
    }
}
</script>

<style>



</style>