<template>
  <div class="gb-giftcard">
    <h3 class="gb-giftcard-title">Gift Card Value</h3>

    <amount-input value="$50" placeholder="Amount"></amount-input>

    <span class="gb-giftcard-helper">or type your own amount</span>
  </div>
</template>

<script>
  import AmountInput from './inputs/AmountInput.vue'

  export default {
    name: 'GiftCard',
    components: {
      AmountInput
    }
  }
</script>

<style>
.gb-giftcard {
  grid-column: 1 / 1;
  width: 80%;
  max-width: 20rem;
  margin: 1rem auto;
  padding: 1rem;
  background-color: var(--color-beige);
  border-radius: 0.5rem;
}

.gb-giftcard-title {
  font-weight: 700;
  font-family: var(--font-family-futura);
  text-transform: uppercase;
}

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

.gb-giftcard-helper {
  display: block;
  margin: 1rem 0;
  color: var(--color-gray);
  font-weight: 600;
  font-size: 0.85rem;
  opacity: 0.5;
}
</style>
