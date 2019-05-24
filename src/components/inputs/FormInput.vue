<template>
  <p class="gb-form-row">
    <label class="gb-form-label" :for="name" :aria-labelledby="name">
      <slot></slot>
    </label>

    <textarea v-if="type === 'textarea'"
              class="gb-form-input"
              rows="2"
              :id="name"
              :placeholder="placeholder"></textarea>

    <input v-else
           class="gb-form-input"
           :id="name"
           :name="name"
           :type="type"
           :placeholder="placeholder" />
  </p>
</template>

<script>
  export default {
    name: 'FormInput',
    props: {
      name: String,
      type: String,
      placeholder: String
    }
  }
</script>

<style lang="scss">
.gb-form-row {
  margin-bottom: 1.5rem;

  @media screen and (min-width: 40rem) {
    display: flex;
  }
}

.gb-form-label {
  display: block;
  flex-basis: 25%;
  margin-right: 1.5rem;
  padding-top: 0.5rem;
  color: var(--color-red);
  font-family: var(--font-family-futura);
  text-align: left;

  @media screen and (min-width: 40rem) {
    text-align: right;
  }
}

.gb-form-input {
  flex: 1;
  width: 100%;
  padding: 0.5rem 0;
  font-size: 1.05rem;
  font-family: var(--font-family-futura);
  border: 0;
  border-bottom: 1px dotted var(--color-beige-dark);
}
</style>
