<template>
    <!-- ciclo di tutti i task -->

    <!-- <ul>
        <li v-for="(task , index) in tasks" :key="index">{{ task.text }}</li>
    </ul> -->

    <!-- se l'array dei task ne ha almeno 1 allora ciclami l'array -->
    <TaskItem v-for="(task, index) in tasks"
        :key="index"
        :task="task"
    />


    <!-- altrimenti mostra un messaggio tipo; 'aggiungi dei task' -->
    <p>No tasks. Add at least one task</p>
</template>

<script>

import TaskItem from './TaskItem.vue'

export default {
    components: { TaskItem },
    props: ['tasks']  
}

</script>

<style scoped></style>