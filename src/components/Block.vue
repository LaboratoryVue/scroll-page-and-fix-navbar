<template>
  <section class="block">
    <h2 class="block__title">block section</h2>
  </section>
</template>

<script>
export default {
  name: 'Block'
}
</script>

<style lang="scss" scoped>
  .block {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: salmon;
    padding: 1rem;
    height: 200px;
    margin: 2rem 0;

    &__title {
      text-transform: capitalize;
    }
  }
</style>
