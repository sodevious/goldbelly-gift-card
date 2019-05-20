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
    btnProp() { return {
        '--btn-bg-color': (this.color),
      }
    }
  }
}
</script>

<style>
  .btn {
    --btn-bg-color: var(--color-red);
    display: inline-block;
    padding: 1rem 2rem;
    margin: 0;
    text-decoration: none;
    text-transform: uppercase;
    appearance: none;
    border: none;
    font-family: var(--font-family-futura);
    font-weight: bold;
    border-radius: 3px;
    background-color: var(--btn-bg-color);
    color: white;
  }
</style>
