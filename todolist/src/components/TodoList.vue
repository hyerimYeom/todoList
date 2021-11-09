<template>
   <div class="row">
        <span class="cell col1"> {{ todo.user }} </span>
        <span class="cell col2"> {{ todo.title }} </span>
        <span class="cell col3"> {{ trimDate }} </span>
        <span class="cell col4"> {{ check }}  </span>
    </div>    
</template>

<script>
export default {
    name : 'TodoList',
    props : { 
        todo : Object,  
    },
    computed : { 
        trimDate: function(){
            return this.todo.endDate.slice(0,10)
        },
        check : function(){
            return this.todo.done === false ? 'X' : 'O'
        }
    }
}
</script>

<style>

</style>