<template>
  <input type="text" class="gb-giftcard-input" />
</template>

<script>
  export default {
    name: 'AmountInput'
  }
</script>

<style>
.gb-giftcard-input {
  display: inline-block;
  width: 50%;
  padding: 1rem;
  font-weight: 700;
  font-size: 2rem;
  font-family: var(--font-family-futura);
  text-align: center;
  background: transparent;
  border: 1px solid transparent;
  border-radius: 0.15rem;
  outline: none;
}

.gb-giftcard-input:hover,
.gb-giftcard-input:focus {
  background-color: var(--color-white);
  border: 1px solid var(--color-beige-dark);
}
</style>
