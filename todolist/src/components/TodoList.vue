<template>
   <div class="row">
        <span class="cell col1"> {{ todo.user }} </span>
        <span class="cell col2" @click="$emit('update', todo.title)"> {{ todo.title }} </span>
        <span class="cell col3"> {{ todoEndDate }} </span>
        <span class="cell col4 cursor-ture" @click="$emit('todo-list')"> {{ todoDone }}  </span>
        <span class="cell col5 cursor-ture" @click="$emit('delete-list')"><span>x</span></span>
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