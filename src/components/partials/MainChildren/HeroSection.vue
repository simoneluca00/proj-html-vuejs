<template>
    <section id="hero">
        <div class="slider">
            <!-- slider con path bg e img dinamico in base al "currentIndex" e il nome delle singole immagini -->
            <div class="singleImage"
                :style="{ backgroundImage: 'url(' + require('@/assets/img/'+ pathBgString) + ')' }"
                @mouseover="stopSlider" @mouseout="startSlide">
                <img :src="require('@/assets/img/' + pathImageString)" alt="pizza slice">
            </div>

            <div class="prev">
                <a @click.prevent="prev" href="">prev</a>
            </div>
            <div class="next">
                <a @click.prevent="next" href="">next</a>
            </div>
        </div>

        <div class="heroCards">
            <!-- v-for con path dinamico per le immagini -->
            <div v-for="i in 4" :key="i" class="hCard">
                <img :src="require('@/assets/img/heroCard' + i + '.jpg')" alt="">
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'HeroSection',

        data() {
            return {
                timer: null,
                currentIndex: 1,
                imagesCount: 3,
            }
        },

        mounted() {
            this.startSlide()
        },

        methods: {
            // slide successiva automaticamente con intervallo settato
            startSlide() {
                this.timer = setInterval(this.next, 3000)
            },

            // stoppare lo slider (hover)
            stopSlider: function () {
                clearInterval(this.timer);
                this.timer = null;
            },

            // slide successiva (click)
            next: function () {
                this.currentIndex += 1;
                if (this.currentIndex > this.imagesCount) {
                    this.currentIndex = 1;
                }
            },

            // slide precedente (click)
            prev: function () {
                this.currentIndex -= 1;
                if (this.currentIndex < 1) {
                    this.currentIndex = this.imagesCount;
                }
            }
        },

        computed: {

            // genera path dinamico in per immagine di background
            pathBgString(){
                return `hero${this.currentIndex}a.png`
            },
            
            // genera path dinamico in per immagine centrale (trancio)
            pathImageString(){
                return `hero${this.currentIndex}b.png`
            },

        }

    }
</script>

<style lang="scss">
    @import '../../../style/global.scss';

    #hero {
        .slider {

            .singleImage {
                @include compileFlex(nowrap, center, center);
                background-repeat: no-repeat;
                background-position: center;
                padding: 20px 0;
                height: 65vh;
                position: relative;


                img {
                    height: 100%;
                }
            }

            .prev,
            .next {
                position: absolute;
                top: 40%;
                background-color: $white;
                padding: 10px 20px;
                border-top-left-radius: 68px;
                border-top-right-radius: 68px;

                a{
                    color: $text-primary;
                    text-decoration: none;
                    position: relative;
                    top: 5px;
                } 
            }

            .prev {
                left: -10px;
                transform: rotate(90deg);
            }

            .next {
                right: -10px;
                transform: rotate(270deg);
            }

        }

        .heroCards {
            @include compileFlex(nowrap, center, center);
            background-color: $white;
            padding: 5px;

            .hCard {
                width: 25%;
                padding: 5px;
                
                img {
                    width: 100%;
                }
            }
        }
    }
</style>