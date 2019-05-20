<template>
  <p class="gb-form-row">
    <label class="gb-form-label" :for="name" :aria-labelledby="name">
      <slot></slot>
    </label>

    <textarea v-if="type === 'textarea'"
              class="gb-form-input"
              rows="3"
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

<style>
  .gb-form-row {
    display: flex;
  }

  .gb-form-label {
    flex-basis: 30%;
    margin-right: 1rem;
    padding-top: 0.5rem;
    color: var(--color-red);
    font-size: 1.05rem;
    font-family: var(--font-family-futura);
    text-align: left;
  }

  .gb-form-input {
    flex: 1;
    padding: 0.5rem;
    font-size: 1.05rem;
    font-family: var(--font-family-futura);
    border: 0;
    border-bottom: 1px dotted var(--color-beige-dark);
  }
</style>
