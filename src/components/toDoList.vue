<template>
    <div>
        <uL>
            <listItem 
                v-for="(todo, index) in todos" :key="index"
                v-bind:todo = "todo"
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
        }
    }
</script>

<style>

</style>