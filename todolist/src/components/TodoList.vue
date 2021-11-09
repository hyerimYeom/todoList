<template>
   <div class="row">
        <span class="cell col1"> {{ todo.user }} </span>
        <span class="cell col2"> {{ todo.title }} </span>
        <span class="cell col3"> {{ todo.endDate }} </span>
        <span class="cell col4"> {{ todo.done }}  </span>
    </div>    
</template>

<script>
export default {
    name : 'TodoList',
    props : { 
        todo : Object,  
    },
    computed : { 
        
    }
}
</script>

<style>

</style>