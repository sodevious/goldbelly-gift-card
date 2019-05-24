<template>
  <div class="gb-giftcard-autocomplete">
    <input v-model="value"
           v-on:click="toggleDropdown"
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

    <div class="gb-giftcard-autocomplete-error" v-show="value < 25 || value > 500">
      Please enter a dollar amount between $1 and $500.
    </div>
  </div>
</template>

<script>
  export default {
    name: 'AmountInput',
    data() {
      return {
        value: '100',
        amounts: ['25', '50', '100', '200'],
        isOpen: false
      };
    },
    methods: {
      toggleDropdown() {
        this.isOpen = !this.isOpen;
      },
      handleOffClick(event) {
        if (!this.$el.contains(event.target)) {
          this.isOpen = false;
        }
      },
      setAmount(amount) {
        this.value = amount;
        this.isOpen = false;
      }
    },
    mounted() {
      document.addEventListener('click', this.handleOffClick)
    },
    destroyed() {
      document.removeEventListener('click', this.handleOffClick)
    }
  }
</script>

<style lang="scss">
.gb-giftcard-autocomplete {
  position: relative;
  display: inline-block;
  box-sizing: border-box;
  width: 50%;
  min-width: 8rem;
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
  transition: 0.25s ease-in all;

  &:hover,
  &:focus {
    background-color: var(--color-white);
    border: 1px solid var(--color-blue);
    box-shadow: 0px 0px 5px rgba(0,0,0,0.1);
  }
}

.gb-giftcard-results {
  position: absolute;
  z-index: 5;
  box-sizing: border-box;
  width: 100%;
  margin-top: -3px;
  padding: 0;
  background-color: var(--color-white);
  border-right: 1px solid var(--color-blue);
  border-bottom: 1px solid var(--color-blue);
  border-left: 1px solid var(--color-blue);
  border-bottom-right-radius: 0.25rem;
  border-bottom-left-radius: 0.25rem;
}

.gb-giftcard-result-item {
  box-sizing: border-box;
  margin: 0;
  padding: 1rem;
  list-style-type: none;
  cursor: pointer;

  &:hover {
    background-color: var(--color-beige);
  }

  &:last-child {
    border-bottom-right-radius: 0.25rem;
    border-bottom-left-radius: 0.25rem;
  }
}

.gb-giftcard-autocomplete-error {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  padding: 1rem;
  background: var(--color-red);
}
</style>
