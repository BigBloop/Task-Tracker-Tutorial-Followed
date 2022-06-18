<template>
    <div>
        <div v-for="(task, tasks) in tasks" :key="tasks">
            <Task @delete-task="$emit('delete-task', task.id)" :task="task" />
        </div>
    </div>
</template>

<script>
    import Task from './Task'
    export default {
        name: 'TasksItem',
        props: {
            tasks: Array,
        },
        components: {
            Task
        },
        emits: ['delete-task'],
    }
</script>