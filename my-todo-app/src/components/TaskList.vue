<template>
    <div v-if="tasks.length">
        <TaskItem v-for="(task, index) in tasks"
            :key="index"
            :task="task"
            @edit ="() => $emit('edit-task', task, index)"
            @remove ="() => $emit('remove-task', index)"
        />
    </div>
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