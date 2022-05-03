<template>
    <section id="clients">
        <div class="container-clients">
            <div class="singleClient" v-for="(element,i) in clients" :key="i">
                <img :src="require('@/assets/img/' + element.logo + '.png')" :alt="'logo di' + element.name">
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'ClientsSection',

        data() {
            return {
                clients: [{
                        name: 'Big Cheese',
                        logo: 'h1-clients-img-1'
                    },
                    {
                        name: 'Bludoos Bar',
                        logo: 'h1-clients-img-2'
                    },
                    {
                        name: 'Gordon',
                        logo: 'h1-clients-img-3'
                    },
                    {
                        name: 'Cowboy',
                        logo: 'h1-clients-img-4'
                    },
                    {
                        name: 'Vegan',
                        logo: 'h1-clients-img-5'
                    },
                ]
            }
        }

    }
</script>

<style lang="scss" scoped>
    @import '@/style/global.scss';

    #clients {
        background-color: $bg-icons-primary;
        padding: 50px 0;

        .container-clients {
            @include compileFlex(wrap, initial, center);

            width: 70%;
            margin: 0 auto;

            .singleClient {
                width: 20%;

                img {
                    width: 100%;
                }
            }
        }
    }
</style>