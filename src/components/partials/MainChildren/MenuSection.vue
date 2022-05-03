<template>
    <section id="menu">

        <svg xmlns="http://www.w3.org/2000/svg" width="18" viewBox="0 0 18 23" class="slice-icon-circle">
            <g fill="#D2401E">
                <path
                    d="M18 19.9c0-.1 0-.2-.1-.2 0-.1 0-.1-.1-.2 0-.1-.1-.3-.2-.6l-.3-.8c-.2-.4-.4-1.1-.6-1.5L10.4 1.2C10.3.8 9.9 0 9.1 0H9h-.1c-.8 0-1.2.8-1.3 1.2L1.3 16.6c-.2.4-.4 1.1-.6 1.5l-.3.8c-.1.3-.2.5-.2.6 0 .1-.1.1-.1.2s-.1.2-.1.3c-.1.3 0 .7.4 1.1.1 0 .1.1.2.1.1.1.3.2.5.3.2 0 2.8 1.5 7.6 1.5h.6c4.8 0 7.4-1.5 7.5-1.6.2-.1.4-.2.5-.3.1-.1.2-.1.2-.2.5-.3.5-.7.5-1zm-7.2-15l1 2.5c-.3.1-.6.2-.9 0-.3-.1-.6-.3-.8-.7-.1-.2-.2-.6-.1-.9.2-.4.4-.6.8-.9-.1.1 0 .1 0 0zM5.7 8.5c.7.4 1.3.9 1.6 1.6.3.7.3 1.6 0 2.3-.3.8-.9 1.3-1.6 1.7-.7.3-1.5.3-2.2 0l2.2-5.6zm-2.6 6.6c1 .4 2.1.4 3-.1 1-.4 1.8-1.2 2.2-2.2.4-1 .4-2.1 0-3.1-.5-1-1.2-1.7-2.2-2.1l2.4-6c.2-.3.3-.6.4-.6 0 .1.1.1.1.1s.1 0 .1-.1c.1 0 .2.2.4.6l1 2.4h-.2c-.6.3-1 .8-1.2 1.4-.3.6-.2 1.3.1 1.8.3.6.8 1 1.4 1.2.5.2 1.1.2 1.7-.1l3.5 8.6c.1.3.3.8.5 1.2h-.2c-.1 0-6.4 3.3-14.2 0h-.1c.2-.4.4-.9.5-1.2l.8-1.8zm13.2 5.4s-2.4 1.4-7 1.4h-.6c-4.6 0-7-1.4-7-1.4-.4-.2-.7-.4-.7-.4s.1-.3.3-.7l.1-.1.1.1c4.3 1.8 8.2 1.7 10.6 1.3 2.7-.4 4.4-1.3 4.4-1.4h.1l.1.1c.1.3.3.6.3.6 0 .1-.3.3-.7.5z" />
                <path
                    d="M11.2 18.4c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2c.1 1.1.9 2 2 2zm0-2.9c.5 0 .9.4.9.9s-.4.9-.9.9-.9-.4-.9-.9.4-.9.9-.9z" />
            </g>
        </svg>

        <div class="text-center">
            <h5 class="pseudo-title fw-400">choose your flavor</h5>
            <h2 class="fw-500">the best pizza menu in town</h2>
            <p class="main-caption fw-300">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ut blandit arcu in
                pretium molestie. Interdum et malesuada fames ac.</p>
        </div>

        <div class="products-wrapper">

            <ul class="products">
                <li class="singleProduct" v-for="(element,i) in products" :key="i">

                    <!-- NOTE img pizza -->
                    <img :src="require('@/assets/img/'+ element.image + '.png')" :alt="'pizza ' + element.name">

                    <!-- NOTE nome pizza -->
                    <h4 class="productName fw-500">{{element.name}}</h4>

                    <div>
                        <!--  NOTE condizione per controllare se è presente uno sconto sul prodotto -->
                        <span v-if="element.initialPrice !== null" class="initialPrice">{{element.initialPrice}}</span>

                        <!-- NOTE prezzo attuale del prodotto -->
                        <span class="currentPrice">{{element.currentPrice}}</span>
                    </div>

                    <!-- NOTE condizione per etichetta SOLD sulla base di una variabile booleana presente nell'oggetto() -->
                    <div v-show="element.sold" class="soldProduct">sold</div>
                </li>
            </ul>

        </div>

    </section>
</template>

<script>
    export default {
        name: 'MenuSection',

        data() {
            return {
                products: [{
                        name: 'bismarck',
                        image: 'h3-product-img-1a',
                        initialPrice: '$35.00',
                        currentPrice: '$30.00',
                        sold: false,
                    },
                    {
                        name: 'fiori di zucca',
                        image: 'h3-product-img-2a',
                        currentPrice: '$30.00',
                        initialPrice: null,
                        sold: true,
                    },
                    {
                        name: 'valdostana',
                        image: 'h3-product-img-3a',
                        currentPrice: '$7.00 - $50.00',
                        initialPrice: null,
                        sold: false,
                    },
                    {
                        name: 'pizza tartufata',
                        image: 'h3-product-img-4a',
                        currentPrice: '$45.00',
                        initialPrice: null,
                        sold: false,
                    },
                    {
                        name: 'francescana',
                        image: 'h3-product-img-5a',
                        currentPrice: '$25.00',
                        initialPrice: '$35.00',
                        sold: true,
                    },
                    {
                        name: 'campagnola',
                        image: 'h3-product-img-6a',
                        currentPrice: '$50.00 - $95.00',
                        initialPrice: null,
                        sold: false,
                    },
                ]
            }
        },

    }
</script>

<style lang="scss" scoped>
    @import '@/style/global.scss';

    #menu {
        padding: 70px 0;
        position: relative;

        h5.pseudo-title {
            color: $text-primary;
            letter-spacing: 0.08em;
        }

        h2 {
            color: $text-dark;
            margin: 10px 0;
            letter-spacing: 0.05em;
        }

        .main-caption {
            color: #8F8F8F;
            max-width: 450px;
            margin: 0 auto;
            text-transform: initial;
            font-family: sans-serif;
            font-size: 0.8em;
        }

        .products {
            @include compileFlex(nowrap, space-around, center);
            margin-top: 80px;

            .singleProduct {
                @include compileFlex(initial, center, center);
                flex-direction: column;
                width: 150px;
                position: relative;

                img {
                    width: 100%;
                    height: 150px;
                }

                h4.productName {
                    color: $text-camel;
                    margin: 10px 0 5px 0;
                }

                .initialPrice {
                    margin-right: 10px;
                    color: $text-initialPrice;
                    text-decoration: line-through;
                }

                .currentPrice {
                    color: $text-primary;
                }

                .initialPrice,
                .currentPrice {
                    font-size: 0.9em;
                }

                .soldProduct {
                    position: absolute;
                    top: 0;
                    right: 0;
                    background-color: $bg-btn-primary;
                    color: $white;
                    padding: 12px 8px;
                    border-radius: 50%;
                    font-size: 0.8em;
                }
            }
        }

        .slice-icon-circle {
            top: 30%;
        }
    }
</style>