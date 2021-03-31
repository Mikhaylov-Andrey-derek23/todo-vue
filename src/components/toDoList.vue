<template>
    <div>
        <uL>
            <listItem 
                v-for="(todo, index) in todos" :key="index"
                v-bind:todo = "todo"
                v-bind:index = "index"
                v-on:remove-todo = "remove" 
            />
        </uL>
    </div>
</template>

<script>

    import listItem from "@/components/listItem";
    export default {
        props:  ['todos'],
        components: {
           listItem 
        },
        methods : {
            remove(id){
                this.$emit('remove-todo', id) 
            }
        }
    }

</script>

<style scoped>
    ul{
        list-style : none;
        margin: 0px;
        padding : 0px;
    }
</style>