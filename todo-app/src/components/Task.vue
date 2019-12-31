<template>
  <div class="task">
      <div class="task__box" @click="done = !done" :class="{ done: done }">
          <div class="task__box--close" :class="{ done__close: done }" @click="destroy"> x </div>
          <div class="task__box--name" :class="{ done__name: done }"> {{ name }} </div>
      </div>
  </div>
</template>

<script>
export default {
    methods: {
        destroy(){
            this.$el.parentNode.removeChild(this.$el); // Funciona de maneira similar bem
            /* O elemento não pode deletar ele mesmo. A solução seria algum evento que alertasse o elemento pai e ele pudesse deletar o elemento filho. */
        },
    },
    props: {
        name: String,
        done: Boolean
    }
}
</script>

<style lang="scss" scoped>
    .task {
        display: flex;
        justify-content: center;
        align-items: center;

        margin: 4px;

        &__box {
            display: flex;
            flex-direction: column;
            
            height: 10rem;
            width: 24rem;
            background-color: #ED4C67;
            border-left: 1rem solid #B53471;
            border-radius: 4px;

            &--name {
                align-self: center;
                font-size: 1.6rem;
            }

            &--close {
                margin: 1rem;
                align-self: flex-end;

                display: flex;
                justify-content: center;
                align-items: center;

                font-size: 1.5rem;
                height: 2rem;
                width: 2rem;
                color: #FFF;
                background-color: #B53471;
                border-radius: 50%;
                cursor: pointer;
            }
        }
    }

    .done {
        background-color: rgb(37, 138, 59);
        border-left: 1rem solid rgb(120, 199, 137);

        &__close {
            background-color: rgb(13, 99, 32);
        }

        &__name {
            text-decoration: line-through;
        }
    }

    
</style>