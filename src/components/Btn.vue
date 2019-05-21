<template>
  <button class="btn" :style="btnProp">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    name: 'Btn',
    props: {
      color: String,
    },
    computed: {
      btnProp() {
        return {
          '--btn-bg-color': (this.color),
        }
      }
    }
  }
</script>

<style>

</style>
