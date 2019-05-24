<template>
  <div class="gb-giftcard" v-bind:class="{ 'is-flipped': swapCard }">
    <h3 v-show="!swapCard" class="gb-giftcard-title">Gift Card Value</h3>

    <amount-input v-show="!swapCard" value="$50" placeholder="Amount"></amount-input>

    <span v-if="!swapCard" class="gb-giftcard-helper">or type your own amount</span>
    <span v-else class="gb-giftcard-helper">Your gift card is on it's way!</span>
  </div>
</template>

<script>
  import AmountInput from './inputs/AmountInput.vue'

  export default {
    name: 'GiftCard',
    props: {
      swapCard: Boolean,
    },
    components: {
      AmountInput
    }
  }
</script>

<style lang="scss">
.gb-giftcard {
  display: flex;
  flex-flow: column;
  align-items: center;
  justify-content: center;
  width: 80%;
  max-width: 20rem;
  height: 12rem;
  margin: 0 auto;
  margin-top: 2rem;
  padding: 1rem;
  background-color: var(--color-beige);
  border-radius: 0.5rem;
  backface-visibility: hidden;
  transition: 0.75s ease-out all;
}

.gb-giftcard-title {
  font-weight: 700;
  font-family: var(--font-family-futura);
  text-transform: uppercase;
}

.gb-giftcard-helper {
  display: block;
  margin: 1rem 0;
  color: var(--color-gray);
  font-weight: 600;
  font-size: 0.85rem;
  opacity: 0.5;
}

.is-flipped {
  background: var(--color-gray);
  transform: rotateY(360deg);

  .gb-giftcard-helper {
    color: var(--color-beige);
    font-size: 1.25rem;
    opacity: 1;
  }
}
</style>
