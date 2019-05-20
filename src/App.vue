<template>
  <div id="app">
    <logo class="gb-logo" foreground="var(--color-red)" background="var(--color-beige)"></logo>
    <h2 class="gb-tagline">Give the gift of gourmet food</h2>

    <div class="gb-container">
      <p>Instantly send an e-gift card to be redeemed on Goldbelly.com. Valid online only.</p>
      <btn>test</btn>
    </div>
  </div>
</template>

<script>
import Logo from './components/Logo.vue'
import Btn from './components/Btn.vue'

export default {
  name: 'app',
  components: {
    Logo,
    Btn
  }
}
</script>


<style>
  @import url("https://fonts.googleapis.com/icon?family=Cabin");
  @import url("~normalize.css");

  :root {
    --color-red: #FF4D4F;
    --color-blue: #1BAAD0;
    --color-beige: #F2EEE9;
    --color-beige-dark: #D2CAB6;
    --color-gray: #333333;
    --color-white: #ffffff;

    --font-family-cabin: "Cabin", sans-serif;
    --font-family-futura: "Futura", sans-serif;
  }

  body {
    background-color: var(--color-beige);
    font-family: var(--font-family-cabin);
    text-align: center;
    padding: 2rem 0;
    font-size: 16px;
  }

  .gb-container {
    background-color: var(--color-white);
    max-width: 40rem;
    margin: 1rem auto;
    padding: 0.5rem;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  }

  .gb-logo {
    margin: 1rem 0;
    width: 25%;
  }

  .gb-tagline {
    font-size: 1rem;
    margin: 0.5rem 0 2rem 0;
    color: var(--color-gray);
    text-transform: uppercase;
    font-family: var(--font-family-futura);
  }
</style>
