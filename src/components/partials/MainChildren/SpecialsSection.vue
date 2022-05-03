<template>
    <section id="specials">

        <div class="img-specials">
            <img src="@/assets/img/h1-img-4.jpg" alt="img sezione specials">
        </div>

        <div class="text-specials">
            <div class="combos">
                <h2>specials*</h2>
                <p class="main-caption fw-300">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Praesent ut.
                </p>

                <!-- NOTE v-for che stampa dinamicamente le info delle singole combo presenti nel menu -->
                <div class="combo-list" v-for="(item,i) in specials" :key="i">
                    <div>
                        <span class="combo-price fw-500">
                            {{item.price}}
                        </span>
                    </div>

                    <div>
                        <span class="combo-name fw-500">
                            {{item.name}}
                        </span>
                        <p class="sub-caption fw-300">{{item.caption}}</p>
                    </div>
                </div>
            </div>

            <svg xmlns="http://www.w3.org/2000/svg" width="18" viewBox="0 0 18 23" class="slice-icon-circle">
                <g fill="#D2401E">
                    <path
                        d="M18 19.9c0-.1 0-.2-.1-.2 0-.1 0-.1-.1-.2 0-.1-.1-.3-.2-.6l-.3-.8c-.2-.4-.4-1.1-.6-1.5L10.4 1.2C10.3.8 9.9 0 9.1 0H9h-.1c-.8 0-1.2.8-1.3 1.2L1.3 16.6c-.2.4-.4 1.1-.6 1.5l-.3.8c-.1.3-.2.5-.2.6 0 .1-.1.1-.1.2s-.1.2-.1.3c-.1.3 0 .7.4 1.1.1 0 .1.1.2.1.1.1.3.2.5.3.2 0 2.8 1.5 7.6 1.5h.6c4.8 0 7.4-1.5 7.5-1.6.2-.1.4-.2.5-.3.1-.1.2-.1.2-.2.5-.3.5-.7.5-1zm-7.2-15l1 2.5c-.3.1-.6.2-.9 0-.3-.1-.6-.3-.8-.7-.1-.2-.2-.6-.1-.9.2-.4.4-.6.8-.9-.1.1 0 .1 0 0zM5.7 8.5c.7.4 1.3.9 1.6 1.6.3.7.3 1.6 0 2.3-.3.8-.9 1.3-1.6 1.7-.7.3-1.5.3-2.2 0l2.2-5.6zm-2.6 6.6c1 .4 2.1.4 3-.1 1-.4 1.8-1.2 2.2-2.2.4-1 .4-2.1 0-3.1-.5-1-1.2-1.7-2.2-2.1l2.4-6c.2-.3.3-.6.4-.6 0 .1.1.1.1.1s.1 0 .1-.1c.1 0 .2.2.4.6l1 2.4h-.2c-.6.3-1 .8-1.2 1.4-.3.6-.2 1.3.1 1.8.3.6.8 1 1.4 1.2.5.2 1.1.2 1.7-.1l3.5 8.6c.1.3.3.8.5 1.2h-.2c-.1 0-6.4 3.3-14.2 0h-.1c.2-.4.4-.9.5-1.2l.8-1.8zm13.2 5.4s-2.4 1.4-7 1.4h-.6c-4.6 0-7-1.4-7-1.4-.4-.2-.7-.4-.7-.4s.1-.3.3-.7l.1-.1.1.1c4.3 1.8 8.2 1.7 10.6 1.3 2.7-.4 4.4-1.3 4.4-1.4h.1l.1.1c.1.3.3.6.3.6 0 .1-.3.3-.7.5z" />
                    <path
                        d="M11.2 18.4c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2c.1 1.1.9 2 2 2zm0-2.9c.5 0 .9.4.9.9s-.4.9-.9.9-.9-.4-.9-.9.4-.9.9-.9z" />
                </g>
            </svg>

        </div>
    </section>
</template>

<script>
    export default {
        name: 'SpecialsSection',

        data() {
            return {
                specials: [{
                        name: 'combo piccolo',
                        price: '$10',
                        caption: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Praesent ut aliquam dui.'
                    },
                    {
                        name: 'combo medio',
                        price: '$20',
                        caption: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Praesent ut aliquam dui.'
                    },
                    {
                        name: 'combo grande',
                        price: '$30',
                        caption: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Praesent ut aliquam dui.'
                    },
                ],
            }
        }

    }
</script>

<style lang="scss" scoped>
    @import '@/style/global.scss';

    #specials {
        @include compileFlex(nowrap, center, center);
        padding-top: 5px;
        background-color: $bg-white-opac;
        min-height: 70vh;

        .img-specials,
        .text-specials {
            width: 50%;
        }

        .img-specials {

            img {
                width: 100%;
                height: 100%;
            }
        }

        .text-specials,
        .combos {
            height: 100%;
        }

        .text-specials {
            @include compileFlex(nowrap, center, center);
            position: relative;

            .combos {
                width: 55%;
                padding: 50px 0;
                overflow-y: auto;

                &::-webkit-scrollbar {
                    display: none;
                }

                h2 {
                    font-size: 2.6em;
                }

                p {
                    text-transform: initial;
                }

                p.main-caption {
                    color: $text-caption;
                    margin-bottom: 50px;
                }

                .combo-list {
                    margin: 30px 0;
                    display: flex;

                    .combo-price {
                        color: $text-dark-primary;
                        margin-right: 10px;
                    }

                    .combo-price,
                    .combo-name {
                        font-size: 1.4em;
                    }

                    .sub-caption {
                        color: $text-subcaption;
                        font-size: 0.9em;
                        max-width: 300px;
                    }
                }
            }

            .slice-icon-circle {
                bottom: 25px;
            }
        }
    }
</style>