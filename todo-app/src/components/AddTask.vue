<template>
  <div class="input">
      <input type="text" class="input__bar" placeholder="Nova tarefa?" v-model="taskName">
      <button class="input__bar--button" @click="addTask">+</button>
  </div>
</template>

<script>
export default {
    data(){
        return {
            taskName: '',
            state: false
        }
    },
    methods: {
        addTask() {
            this.$emit('taskAdded', {
                name: this.taskName,
                state: false
            })
        }
    }
}
</script>

<style lang="scss" scoped>
.input {
    display: flex;
    justify-content: center;

    margin: 2rem;

    &__bar {
        display: flex;
        justify-content: center;
        align-items: center;

        padding: .5rem;

        height: 3rem;
        width: 24rem;
        border: 1px solid #FFF;
        border-right: 0px;
        border-radius: 4px 0 0 4px;
        background-color: rgba(0, 0, 0, .2);

        font-size: 1.8rem;
        color: #FFF;

            &--button {
                width: 3rem;
                border: 1px solid #FFF;
                background-color: darkcyan;
                color: #FFF;
                font-size: 1.8rem;
                font-weight: bold;
                cursor: pointer;
            }
    }
}
</style>