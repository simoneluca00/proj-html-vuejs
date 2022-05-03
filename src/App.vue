<template>
  <div id="app">
    <header>
      <HeaderPizza />
    </header>

    <main>
      <MainPizza />

      <!-- NOTE sezione BOOKING fuori dal comp. "main" per facilitare il passaggio dei dati dagli input -->
      <BookingSection />
    </main>

    <FooterPizza />

  </div>
</template>

<script>
  import HeaderPizza from './components/HeaderPizza.vue';
  import MainPizza from './components/MainPizza.vue';
  import FooterPizza from './components/FooterPizza.vue';
  import BookingSection from './components/partials/BookingSection.vue'

  export default {
    name: 'App',

    components: {
      HeaderPizza,
      MainPizza,
      FooterPizza,
      BookingSection,
    },

  }
</script>

<style lang="scss">
  @import './style/global.scss';
  @import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;400;500;600;700&display=swap');

  // ANCHOR RESET
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Oswald', sans-serif;
    text-transform: uppercase;
    letter-spacing: 0.03em;
  }

  html {
    scroll-behavior: smooth;
  }

  a {
    text-decoration: none;
  }

  ul {
    list-style-type: none;
  }

  // ANCHOR UTILITY
  .btn {
    border: none;
    font-size: 1em;
    padding: 8px 20px;
    cursor: pointer;

    &:active {
      transform: scale(0.9);
      font-size: 0.95em;
      box-shadow: 0px 4px 8px $text-dark-primary;
    }
  }

  .btn-primary {
    background-color: $bg-btn-primary;
    color: $white;
  }

  .slice-icon-circle {
    position: absolute;
    right: 10px;
    width: 45px;
    height: 45px;
    clip-path: circle();
    background-color: $bg-icons-primary;
    border: 10px solid $bg-icons-primary;
  }

  .bg-white {
    background-color: $white;
  }

  .mr-5 {
    margin-right: 5px;
  }

  .text-center {
    text-align: center;
  }

  .fw-300 {
    font-weight: 300;
  }

  .fw-400 {
    font-weight: 400;
  }

  .fw-500 {
    font-weight: 500;
  }

  .fw-600 {
    font-weight: 600;
  }

  .fw-700 {
    font-weight: 700;
  }

  // ANCHOR CONTENITORE GENERALE "APP"
  #app {

    header {
      padding: 20px 0;
      background: $bg-dark-stars;
    }
  }
</style>