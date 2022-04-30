<template>
  <section id="container-mosaic">
    <div class="part1 side"></div>
    <div class="part2 centerX"></div>
    <div class="part3 side"></div>
    <div class="part4 side centerY"></div>
    <div class="part5 centerX"></div>
    <div class="part6 side centerY">
      <svg xmlns="http://www.w3.org/2000/svg" width="18" viewBox="0 0 18 23" class="slice-icon-circle">
        <g fill="#D2401E">
          <path
            d="M18 19.9c0-.1 0-.2-.1-.2 0-.1 0-.1-.1-.2 0-.1-.1-.3-.2-.6l-.3-.8c-.2-.4-.4-1.1-.6-1.5L10.4 1.2C10.3.8 9.9 0 9.1 0H9h-.1c-.8 0-1.2.8-1.3 1.2L1.3 16.6c-.2.4-.4 1.1-.6 1.5l-.3.8c-.1.3-.2.5-.2.6 0 .1-.1.1-.1.2s-.1.2-.1.3c-.1.3 0 .7.4 1.1.1 0 .1.1.2.1.1.1.3.2.5.3.2 0 2.8 1.5 7.6 1.5h.6c4.8 0 7.4-1.5 7.5-1.6.2-.1.4-.2.5-.3.1-.1.2-.1.2-.2.5-.3.5-.7.5-1zm-7.2-15l1 2.5c-.3.1-.6.2-.9 0-.3-.1-.6-.3-.8-.7-.1-.2-.2-.6-.1-.9.2-.4.4-.6.8-.9-.1.1 0 .1 0 0zM5.7 8.5c.7.4 1.3.9 1.6 1.6.3.7.3 1.6 0 2.3-.3.8-.9 1.3-1.6 1.7-.7.3-1.5.3-2.2 0l2.2-5.6zm-2.6 6.6c1 .4 2.1.4 3-.1 1-.4 1.8-1.2 2.2-2.2.4-1 .4-2.1 0-3.1-.5-1-1.2-1.7-2.2-2.1l2.4-6c.2-.3.3-.6.4-.6 0 .1.1.1.1.1s.1 0 .1-.1c.1 0 .2.2.4.6l1 2.4h-.2c-.6.3-1 .8-1.2 1.4-.3.6-.2 1.3.1 1.8.3.6.8 1 1.4 1.2.5.2 1.1.2 1.7-.1l3.5 8.6c.1.3.3.8.5 1.2h-.2c-.1 0-6.4 3.3-14.2 0h-.1c.2-.4.4-.9.5-1.2l.8-1.8zm13.2 5.4s-2.4 1.4-7 1.4h-.6c-4.6 0-7-1.4-7-1.4-.4-.2-.7-.4-.7-.4s.1-.3.3-.7l.1-.1.1.1c4.3 1.8 8.2 1.7 10.6 1.3 2.7-.4 4.4-1.3 4.4-1.4h.1l.1.1c.1.3.3.6.3.6 0 .1-.3.3-.7.5z" />
          <path
            d="M11.2 18.4c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2c.1 1.1.9 2 2 2zm0-2.9c.5 0 .9.4.9.9s-.4.9-.9.9-.9-.4-.9-.9.4-.9.9-.9z" />
        </g>
      </svg>
    </div>
    <div class="part7 side"></div>
    <div class="part8 centerX"></div>
    <div class="part9 side"></div>

    <p>go ahead and <br>
      build your <br>
      own pizza <br>
      we won’t <br>
      judge!
    </p>


  </section>
</template>

<script>
  export default {
    name: 'MosaicPizza',

    data() {
      return {

      }
    }

  }
</script>

<style lang="scss" scoped>
  @import '../../../style/global.scss';

  #container-mosaic {
    @include compileFlex(wrap, initial, initial);
    height: 60vh;
    position: relative;

    div {
      background-image: url('../../../assets/img/h3-background-img.jpg');
    }

    // immagini nei 4 angoli
    .side {
      width: 10%;
      height: 25%;
    }

    // sezione centrale (asse orizzontale)
    .centerX {
      width: 80%;
    }

    // immagine centrale compresa tra i due angoli (sull'asse verticale)
    .side.centerY {
      height: 50%;
    }

    .part1,
    .part2 {
      background-position: bottom right;
    }

    .part5,
    .part8 {
      background-size: 100%;
    }

    .part2 {
      background-size: 110%;
    }

    .part3 {
      background-position: bottom left;
    }

    .part4 {
      background-position: bottom 93% right;
    }

    .part5 {
      background-position: left top;
    }

    .part6 {
      background-position: left -30px top -50px;
      position: relative;

      .slice-icon-circle {
        bottom: 25px;
      }
    }

    .part7 {
      background-position: top 66% right -10px;
      background-size: 1200%;
    }

    .part8 {
      background-position: center bottom 30%;
    }

    .part9 {
      background-position: bottom 38% right 98%;
    }

    p {
      position: absolute;
      left: 24%;
      top: 22%;
      color: $white;
      font-size: 3em;
      font-weight: 500;
      letter-spacing: 0.02em;
      line-height: 1.15em;
    }
  }
</style>