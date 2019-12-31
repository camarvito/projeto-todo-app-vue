<template>
    <div class="task-container">
        <Task v-for="task in tasks" :key="task" :name="task.name" :done="task.done" />
    </div>
</template>

<script>
import Task from '@/components/Task'

export default {
    props: {
        tasks: { type: Array, required: true }
    },
    components: { Task }
}
</script>

<style lang="scss" scoped>
.task-container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
}
</style>