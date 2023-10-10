<template>
    <div v-for="task in tasks" :key="task.id">
            <div>
                <h1>{{ task.task }}</h1>
                <h1>{{ task.date }}</h1>
            </div>
        </div>
</template>

<script>

    export default {
        name:'TaskDisplay',
        prop:{
            tasks: Array,
        }
    }
</script>

<style scoped>

</style>