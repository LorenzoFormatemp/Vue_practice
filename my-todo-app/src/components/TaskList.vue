<template>
    <!-- ciclo di tutti i task -->

    <!-- se l'array dei task ne ha almeno 1 allora ciclami l'array -->

    <div v-if="tasks.length">
        <TaskItem v-for="(task, index) in tasks"
            :key="index"
            :task="task"
            @remove ="() => $emit('remove-task', index)"
        />
    </div>

    <!-- altrimenti mostra un messaggio tipo; 'aggiungi dei task' -->
    <p v-else>No tasks. Add at least one task</p>
</template>

<script>

import TaskItem from './TaskItem.vue'

export default {
    components: { TaskItem },
    props: ['tasks']  
}

</script>

<style scoped></style>