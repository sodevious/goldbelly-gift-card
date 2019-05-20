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
  .btn {
    --btn-bg-color: var(--color-red);
    display: inline-block;
    margin: 0;
    padding: 1rem 2rem;
    color: white;
    font-weight: 700;
    font-family: var(--font-family-futura);
    letter-spacing: 0.15rem;
    text-transform: uppercase;
    text-decoration: none;
    background-color: var(--btn-bg-color);
    border: none;
    border-radius: 0.25rem;
    cursor: pointer;
    appearance: none;
  }

  .btn:hover {
    filter: brightness(80%);
  }
</style>
