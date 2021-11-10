<template>
   <div class="row">
        <span class="cell col1"> {{ todo.user }} </span>
        <span class="cell col2"> {{ todo.title }} </span>
        <span class="cell col3"> {{ todoEndDate }} </span>
        <span class="cell col4" @click="$emit('todoList', todo.done)"> {{ todoDone }}  </span>
    </div>    
</template>

<script>
export default {
    name : 'List',
    props : { 
        todo : Object,  
    },
    methods : {
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