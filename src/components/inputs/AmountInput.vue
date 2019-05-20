<template>
  <div class="gb-giftcard-autocomplete">
    <input v-model="value"
           v-on:click="handleDropdown"
           v-on:input="isOpen == false"
           type="number"
           max="500"
           class="gb-giftcard-input" />

    <ul v-show="isOpen" class="gb-giftcard-results">
      <li v-for="(amount, i) in amounts"
          :key="i"
          @click="setAmount(amount)"
          class="gb-giftcard-result-item">
        {{ amount }}
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'AmountInput',
    data() {
      return {
        value: '100',
        amounts: ['25', '50', '100', '200'],
        isOpen: false,
      };
    },
    methods: {
      handleDropdown() {
        this.isOpen = true;
      },
      handleOffClick(event) {
        if (!this.$el.contains(event.target)) {
          this.isOpen = false;
        }
      },
      setAmount(amount) {
        this.value = amount;
        this.isOpen = false;
      },
    },
    mounted() {
      document.addEventListener('click', this.handleOffClick)
    },
    destroyed() {
      document.removeEventListener('click', this.handleOffClick)
    }
  }
</script>

<style>
.gb-giftcard-autocomplete {
  position: relative;
  display: inline-block;
  box-sizing: border-box;
  width: 50%;
}

.gb-giftcard-autocomplete:after {
  position: absolute;
  top: 1.5rem;
  left: 0.75rem;
  z-index: 6;
  font-weight: 700;
  font-family: var(--font-family-futura);
  opacity: 0.75;
  content: "$";
}

.gb-giftcard-input {
  position: relative;
  box-sizing: border-box;
  width: 100%;
  height: 4rem;
  margin: 0;
  font-weight: 700;
  font-size: 2rem;
  font-family: var(--font-family-futura);
  text-align: center;
  text-indent: 1rem;
  background: transparent;
  border: 1px solid transparent;
  border-radius: 0.25rem;
  outline: none;
  cursor: pointer;
}

.gb-giftcard-input:hover,
.gb-giftcard-input:focus {
  background-color: var(--color-white);
  border: 1px solid var(--color-beige-dark);
}

.gb-giftcard-results {
  position: absolute;
  z-index: 5;
  box-sizing: border-box;
  width: 100%;
  margin-top: -2px;
  padding: 0;
  background-color: var(--color-white);
  border-right: 1px solid var(--color-beige-dark);
  border-bottom: 1px solid var(--color-beige-dark);
  border-left: 1px solid var(--color-beige-dark);
}

.gb-giftcard-result-item {
  box-sizing: border-box;
  margin: 0;
  padding: 1rem;
  list-style-type: none;
  cursor: pointer;
}

.gb-giftcard-result-item:hover {
  background-color: var(--color-beige);
}
</style>
