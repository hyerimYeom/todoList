<template>
   <div class="row">
        <span class="cell col1"> {{ todo.user }} </span>
        <span class="cell col2"> {{ todo.title }} </span>
        <span class="cell col3"> {{ todoEndDate }} </span>
        <span class="cell col4"> {{ todoCheck }}  </span>
    </div>    
</template>

<script>
export default {
    name : 'TodoList',
    props : { 
        todo : Object,  
    },
    computed : { 
        todoEndDate: function(){
            return this.todo.endDate.slice(0,10)
        },
        todoCheck : function(){
            return this.todo.done === false ? 'X' : 'O'
        }
    }
}
</script>

<style>

</style>