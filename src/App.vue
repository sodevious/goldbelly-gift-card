<template>
  <div id="app">
    <logo class="gb-logo" foreground="var(--color-red)" background="var(--color-beige)"></logo>
    <h2 class="gb-tagline">Give the gift of gourmet food</h2>

    <div class="gb-container">
      <p>Instantly send an e-gift card to be redeemed on Goldbelly.com. Valid online only.</p>

      <gift-card></gift-card>

      <form>
        <form-input name="recipientName" type="text">Recipient Name</form-input>
        <form-input name="recipientEmail" type="email" placeholder="food.explorer@goldbelly.com">Recipient Email</form-input>

        <br />

        <form-input name="senderName" type="text">Sender Name</form-input>
        <form-input name="senderEmail" type="email" placeholder="food.explorer@goldbelly.com">Sender Email</form-input>

        <br />

        <form-input name="giftMessage" type="textarea">Gift Message</form-input>
      </form>
    </div>
  </div>
</template>

<script>
  import Logo from './components/Logo.vue'
  import GiftCard from './components/GiftCard.vue'
  import Btn from './components/Btn.vue'
  import FormInput from './components/inputs/FormInput.vue'

  export default {
    name: 'app',
    components: {
      Logo,
      GiftCard,
      Btn,
      FormInput
    }
  }
</script>

<style>
  @import url("https://fonts.googleapis.com/icon?family=Cabin");
  @import url("~normalize.css");

  :root {
    --color-red: #ff4d4f;
    --color-blue: #1baad0;
    --color-beige: #f2eee9;
    --color-beige-dark: #d2cab6;
    --color-gray: #333;
    --color-white: #fff;
    --font-family-cabin: "Cabin", sans-serif;
    --font-family-futura: "Futura", sans-serif;
  }

  body {
    padding: 2rem 0;
    color: var(--color-gray);
    font-family: var(--font-family-cabin);
    text-align: center;
    background-color: var(--color-beige);
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  .gb-container {
    display: block;
    grid-template-rows: auto;
    grid-template-columns: 50% 50%;
    max-width: 40rem;
    margin: 1rem auto;
    padding: 1rem;
    background-color: var(--color-white);
    box-shadow: 0 1rem 1rem rgba(0, 0, 0, 0.1);
  }

  form {
    grid-column: 2 / 2;
  }

  .gb-logo {
    width: 20%;
    min-width: 10rem;
    margin: 1rem 0;
  }

  .gb-tagline {
    margin: 0.5rem 0 2rem 0;
    color: var(--color-gray);
    font-size: 0.9rem;
    font-family: var(--font-family-futura);
    text-transform: uppercase;
  }
</style>
