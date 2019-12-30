<template>
  <div class="progress-bar">
      <div class="progress-bar--value">0%</div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    .progress-bar {
        display: flex;
        justify-content: center;
        align-items: center;

        height: 2.4rem;
        width: 70rem;
        border: 1px solid #FFF;
        border-radius: 4px;

        &--value {
            font-size: 1.6rem;
        }
    }
</style>