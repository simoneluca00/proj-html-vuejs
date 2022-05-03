<template>
    <section id="hero">
        <div class="slider">

            <!-- NOTE SLIDER: path bg e img dinamici in base al valore di "currentIndex" && al nome delle singole immagini -->

            <div class="singleImage" @mouseover="stopSlider" @mouseout="startSlide" 
                :style="{ backgroundImage: 'url(' + require('@/assets/img/'+ pathBgString) + ')' }">

                <img :src="require('@/assets/img/' + pathImageString)" alt="pizza slice">

            </div>

            <div class="prev">
                <a @click.prevent="prev" href="">prev</a>
            </div>

            <div class="next">
                <a @click.prevent="next" href="">next</a>
            </div>

        </div>


        <!-- NOTE cards al di sotto dello slider -->
        <div class="heroCards">

            <!-- NOTE v-for con path dinamico per le immagini-->
            <div v-for="i in cardsCounter" :key="i" 
                class="hCard" :class="[i != cardsCounter ? 'mr-5' : '']"
                @mouseover="showByIndex = i" @mouseout="showByIndex = null">

                <img :src="require('@/assets/img/heroCard' + i + '.jpg')" alt="hero card"
                    :class="[showByIndex === i ? 'opacity-6' : '']">

                <!-- NOTE effetto all'hover basato sul v-show e la variabile "showByIndex" -->
                <div v-show="showByIndex === i">
                    <font-awesome-icon icon="fa-regular fa-eye" />
                </div>

            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'HeroSection',

        data() {
            return {

                // slider
                timer: null,
                currentIndex: 1,
                imagesSlider: 3,

                // hero cards
                cardsCounter: 4,
                showByIndex: null,
            }
        },

        mounted() {
            this.startSlide()
        },

        methods: {
            // NOTE slide successiva automaticamente con intervallo settato
            startSlide() {
                this.timer = setInterval(this.next, 3000)
            },

            // NOTE stoppare lo slider (hover)
            stopSlider() {
                clearInterval(this.timer);
                this.timer = null;
            },

            // NOTE slide successiva (click)
            next() {
                this.currentIndex += 1;
                if (this.currentIndex > this.imagesSlider) {
                    this.currentIndex = 1;
                }
            },

            // NOTE slide precedente (click)
            prev() {
                this.currentIndex -= 1;
                if (this.currentIndex < 1) {
                    this.currentIndex = this.imagesSlider;
                }
            }
        },

        computed: {

            // NOTE genera path dinamico in per immagine di background
            pathBgString() {
                return `hero${this.currentIndex}a.png`
            },

            // NOTE genera path dinamico in per immagine centrale (trancio)
            pathImageString() {
                return `hero${this.currentIndex}b.png`
            },

        }

    }
</script>

<style lang="scss">
    @import '@/style/global.scss';

    .opacity-6 {
        opacity: 0.6;
    }

    #hero {
        background: $bg-dark-stars;

        .singleImage,
        .heroCards {
            @include compileFlex(nowrap, center, center);
        }

        .slider {
            position: relative;
            padding-bottom: 40px;

            .singleImage {
                background-repeat: no-repeat;
                background-position: center;
                padding: 20px 0;
                height: 55vh;
                min-height: 450px;
                transition: all .5s;


                img {
                    height: 100%;
                }
            }

            .prev {
                left: -14px
            }

            .next {
                right: -14px;
            }
        }

        .heroCards {
            background-color: $white;
            padding-top: 5px;

            .hCard {
                width: 25%;
                position: relative;

                &:hover {
                    cursor: pointer;
                }

                img {
                    width: 100%;
                }

                .fa-eye {
                    @include absoluteCenter;

                    color: $white;
                    background-color: $bg-btn-primary;
                    padding: 20px;
                    border-radius: 50%;

                    &:hover {
                        padding: 25px;
                        font-size: 1.2em;
                    }
                }
            }
        }
    }
</style>