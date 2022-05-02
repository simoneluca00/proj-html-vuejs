<template>
    <footer>
        <div id="footer-info">

            <div class="find-us">
                <h3 class="fw-500">find our restaurants</h3>
                <ul>
                    <li class="singleRestaurant" v-for="(element, i) in restaurantsPosition" :key="'a' + i">
                        <span class="fw-400">{{element.address}}</span>
                        <span class="fw-400">{{element.city}}</span>
                        <span class="fw-400">{{element.phoneNumber}}</span>
                    </li>
                    <li class="footer-credits">
                        <span class="credits-intro fw-300">Created with &#9825; by </span>
                        <span class="credits-end fw-300">Qode Interactive</span>
                    </li>
                </ul>
            </div>

            <div class="working-hours">
                <h3 class="fw-500">working hours</h3>

                <ul>
                    <li v-for="(item, i) in workingHours" :key="'b' + i">

                        <div>
                            <h5 class="fw-400">{{item.day}}</h5>
                            <span class="text-primary" v-if="item.day === 'saturday'">*</span>
                        </div>
                        <span
                            :class="(item.restaurantStatus == 'Kitchen Closed') ? 'text-primary' : '' ">{{item.restaurantStatus}}</span>
                    </li>

                    <li class="footer-social">
                        <h5 class="fw-400">follow us:</h5>
                        <div class="social-icons">
                            <a href="#twitter">
                                <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
                                    viewBox="0 0 30 30" width="20px" height="20px">
                                    <g id="surface97211">
                                        <path
                                            style=" stroke:none;fill-rule:nonzero;fill:rgb(100%,100%,100%);fill-opacity:1;"
                                            d="M 28 6.9375 C 27.042969 7.363281 26.015625 7.648438 24.9375 7.777344 C 26.039062 7.117188 26.882812 6.070312 27.28125 4.824219 C 26.25 5.4375 25.109375 5.882812 23.894531 6.121094 C 22.921875 5.085938 21.535156 4.4375 20 4.4375 C 17.054688 4.4375 14.664062 6.824219 14.664062 9.769531 C 14.664062 10.1875 14.714844 10.597656 14.804688 10.984375 C 10.371094 10.761719 6.441406 8.640625 3.808594 5.410156 C 3.351562 6.199219 3.089844 7.113281 3.089844 8.09375 C 3.089844 9.945312 4.027344 11.578125 5.460938 12.53125 C 4.585938 12.503906 3.761719 12.265625 3.042969 11.867188 C 3.042969 11.890625 3.042969 11.910156 3.042969 11.933594 C 3.042969 14.519531 4.882812 16.675781 7.324219 17.164062 C 6.875 17.285156 6.402344 17.351562 5.917969 17.351562 C 5.574219 17.351562 5.238281 17.316406 4.914062 17.253906 C 5.59375 19.375 7.5625 20.917969 9.898438 20.960938 C 8.070312 22.390625 5.773438 23.242188 3.273438 23.242188 C 2.84375 23.242188 2.417969 23.21875 2 23.167969 C 4.359375 24.683594 7.164062 25.566406 10.175781 25.566406 C 19.988281 25.566406 25.351562 17.4375 25.351562 10.386719 C 25.351562 10.15625 25.347656 9.925781 25.335938 9.699219 C 26.378906 8.945312 27.285156 8.007812 28 6.9375 Z M 28 6.9375 " />
                                    </g>
                                </svg>
                            </a>

                            <a href="#facebook">
                                <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
                                    viewBox="0 0 24 24" width="20px" height="20px">
                                    <g id="surface105192">
                                        <path
                                            style=" stroke:none;fill-rule:nonzero;fill:rgb(100%,100%,100%);fill-opacity:1;"
                                            d="M 5 3 C 3.898438 3 3 3.898438 3 5 L 3 19 C 3 20.101562 3.898438 21 5 21 L 19 21 C 20.101562 21 21 20.101562 21 19 L 21 5 C 21 3.898438 20.101562 3 19 3 Z M 5 5 L 19 5 L 19 19 L 14.414062 19 L 14.414062 15.035156 L 16.777344 15.035156 L 17.128906 12.308594 L 14.429688 12.308594 L 14.429688 10.574219 C 14.429688 9.785156 14.648438 9.253906 15.777344 9.253906 L 17.207031 9.253906 L 17.207031 6.820312 C 16.511719 6.75 15.8125 6.714844 15.113281 6.71875 C 13.042969 6.71875 11.621094 7.984375 11.621094 10.308594 L 11.621094 12.3125 L 9.277344 12.3125 L 9.277344 15.039062 L 11.621094 15.039062 L 11.621094 19 L 5 19 Z M 5 5 " />
                                    </g>
                                </svg>
                            </a>

                            <a href="#instagram">
                                <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
                                    viewBox="0 0 24 24" width="20px" height="20px">
                                    <g id="surface96590">
                                        <path
                                            style=" stroke:none;fill-rule:nonzero;fill:rgb(100%,100%,100%);fill-opacity:1;"
                                            d="M 8 3 C 5.242188 3 3 5.242188 3 8 L 3 16 C 3 18.757812 5.242188 21 8 21 L 16 21 C 18.757812 21 21 18.757812 21 16 L 21 8 C 21 5.242188 18.757812 3 16 3 Z M 8 5 L 16 5 C 17.652344 5 19 6.347656 19 8 L 19 16 C 19 17.652344 17.652344 19 16 19 L 8 19 C 6.347656 19 5 17.652344 5 16 L 5 8 C 5 6.347656 6.347656 5 8 5 Z M 17 6 C 16.449219 6 16 6.449219 16 7 C 16 7.550781 16.449219 8 17 8 C 17.550781 8 18 7.550781 18 7 C 18 6.449219 17.550781 6 17 6 Z M 12 7 C 9.242188 7 7 9.242188 7 12 C 7 14.757812 9.242188 17 12 17 C 14.757812 17 17 14.757812 17 12 C 17 9.242188 14.757812 7 12 7 Z M 12 9 C 13.652344 9 15 10.347656 15 12 C 15 13.652344 13.652344 15 12 15 C 10.347656 15 9 13.652344 9 12 C 9 10.347656 10.347656 9 12 9 Z M 12 9 " />
                                    </g>
                                </svg>
                            </a>

                            <a href="#linkedin">
                                <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
                                    viewBox="0 0 32 32" width="20px" height="20px">
                                    <g id="surface1281858">
                                        <path
                                            style=" stroke:none;fill-rule:nonzero;fill:rgb(100%,100%,100%);fill-opacity:1;"
                                            d="M 8.644531 4 C 7.183594 4 6 5.179688 6 6.640625 C 6 8.101562 7.183594 9.308594 8.640625 9.308594 C 10.097656 9.308594 11.285156 8.101562 11.285156 6.640625 C 11.285156 5.183594 10.101562 4 8.644531 4 Z M 21.535156 11 C 19.316406 11 18.046875 12.160156 17.4375 13.3125 L 17.375 13.3125 L 17.375 11.3125 L 13 11.3125 L 13 26 L 17.558594 26 L 17.558594 18.726562 C 17.558594 16.8125 17.703125 14.960938 20.074219 14.960938 C 22.410156 14.960938 22.441406 17.144531 22.441406 18.847656 L 22.441406 26 L 27 26 L 27 17.933594 C 27 13.984375 26.152344 11 21.535156 11 Z M 6.363281 11.3125 L 6.363281 26 L 10.925781 26 L 10.925781 11.3125 Z M 6.363281 11.3125 " />
                                    </g>
                                </svg>
                            </a>

                        </div>
                    </li>
                </ul>
            </div>

            <div class="footer-caption">
                <p>
                    the don peppe crew first and foremost values an authentic well baked slice of pizza.
                </p>
            </div>
            <div class="label-natural">
                <img src="../assets/img/footer-label-natural.png" alt="natural product label">
            </div>
        </div>

        <div id="footer-img"></div>
    </footer>
</template>

<script>
    export default {
        name: 'FooterPizza',

        data() {
            return {
                restaurantsPosition: [{
                        address: '1614 E. Bell Rd #104',
                        city: 'Salerno, AZ 85022',
                        phoneNumber: '(602) 867-1010'
                    },
                    {
                        address: '204 E. Pizzetta Tommaso',
                        city: 'Sorrento, AZ 85022',
                        phoneNumber: '(358) 867-1010'
                    },
                    {
                        address: 'Viale Puglia 54',
                        city: 'Torre Del Greco, AZ 85022',
                        phoneNumber: '(359) 867-1010'
                    },
                    {
                        address: 'Corso Italia AA',
                        city: 'Naples, AZ 85022',
                        phoneNumber: '(081) 867-1010'
                    },
                ],

                workingHours: [{
                        day: 'monday',
                        restaurantStatus: 'Kitchen Closed',
                    },
                    {
                        day: 'tuesday until friday',
                        restaurantStatus: '9 AM - 10 PM',
                    },
                    {
                        day: 'saturday',
                        restaurantStatus: '11 AM - Midnight ',
                    },
                    {
                        day: 'sunday',
                        restaurantStatus: '9 AM - 10 PM',
                    },
                ]
            }
        }

    }
</script>

<style lang="scss" scoped>
    @import '../style/global.scss';

    .text-primary {
        color: $text-primary !important;
    }

    footer {
        display: flex;

        #footer-img {
            width: 50%;
            background-image: url('../assets/img/footer-img-1.jpg');
            background-repeat: no-repeat;
            background-position: top 65% center;
            background-size: cover;
        }

        #footer-info {
            @include compileFlex(initial, space-between, initial);
            position: relative;
            background: $bg-dark-stars;
            padding: 30px 20px 20px 20px;
            width: 50%;

            .find-us,
            .working-hours,
            .footer-caption {
                padding: 30px 0;
            }

            span {
                text-transform: initial;
                color: $text-footer;
                font-family: sans-serif;
                font-size: 0.85em;
            }

            h3 {
                color: $text-camel;
            }

            ul {
                list-style-type: none;

                li:not(.footer-credits, .footer-social) {
                    display: flex;
                    flex-direction: column;
                    margin: 25px 0;
                }
            }

            .find-us {

                li:not(.footer-credits) {
                    span {
                        margin-bottom: 5px;
                    }
                }

                .footer-credits {
                    font-size: 0.9em;
                    margin-top: 70px;

                    .credits-intro {
                        color: $text-camel;
                    }

                    .credits-end {
                        color: #339966;
                    }
                }
            }

            .working-hours {

                li {

                    h5 {
                        color: $text-camel;
                        margin-right: 3px;
                    }

                    div {
                        display: flex;

                        span {
                            font-size: 1.2em !important;
                        }
                    }
                }

                .footer-social {
                    display: flex;
                    align-items: center;
                    margin-top: 50px;

                    a {
                        height: 20px;
                        margin: 0 2px;
                    }
                }
            }

            .footer-caption {
                width: 40%;

                p {
                    width: 240px;
                    max-width: 90%;
                    margin: 0 auto;
                    color: $white;
                    font-size: 1.6em;
                }
            }

            .label-natural {
                position: absolute;
                bottom: 10px;
                right: 10px;
                width: 150px;

                img {
                    width: 100%;
                }
            }
        }

    }
</style>