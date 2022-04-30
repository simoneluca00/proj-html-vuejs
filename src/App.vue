<template>
  <div id="app">
    <header>
      <HeaderPizza />
    </header>

      <MainPizza />

      
  </div>
</template>

<script>
  import HeaderPizza from './components/HeaderPizza.vue';
  import MainPizza from './components/MainPizza.vue';

  export default {
    name: 'App',

    components: {
      HeaderPizza,
      MainPizza,
    },

  }
</script>

<style lang="scss">
  @import './style/global.scss';
  @import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200;300;400;500;600;700&display=swap');

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

  // ANCHOR UTILITY
    .btn {
      border: none;
      font-size: 1em;
      padding: 8px 20px;
      cursor: pointer;

      &:active {
        transform: scale(1.1);
      }
    }

  .slice-icon-circle {
    position: absolute;
    right: 10px;
    width: 45px;
    height: 45px;
    border-radius: 50%;
    background-color: $bg-icons-primary;
    border: 10px solid $bg-icons-primary;
  }

    .bg-white {
      background-color: $white;
    }

    .mr-5 {
      margin-right: 5px;
    }

  #app {
    // il background stellato sull'intero "body" perchè si ripete in più sezioni
    background: $bg-dark-stars;

    header {
      padding: 20px 0;
    }

    .btn-primary {
      background-color: $bg-btn-primary;
      color: $white;
    }
  }
</style>