<template>
    <section id="events">
        <div class="events-wrapper">
            <div class="events-list">

                <div class="events-title">
                    <h5 class="fw-500">made with love</h5>
                    <h2 class="fw-400">delish pizza deals</h2>
                </div>

                <ul>

                    <!-- ternario per impostare la classe (border-bottom) a tutti gli elementi eccetto l'ultimo  -->
                    <li class="single-event" :class="(i !== events.length - 1) ? 'border-events' : ''" v-for="(element,i) in events" :key="i">
                        <div class="event-date">
                            <span class="event-day fw-600">{{element.day}}</span>
                            <span class="event-month fw-400">{{element.month}}</span>
                        </div>

                        <div class="event-details">
                            <p class="event-name fw-400">{{element.name}}</p>
                            <div class="event-location">
                                <font-awesome-icon icon="fa-solid fa-location-dot" />
                                <span class="fw-300">{{element.location}}</span>
                            </div>
                        </div>
                    </li>
                </ul>

            </div>

            <div class="bg-white"></div>

        </div>

        <div class="events-bg"></div>

        <svg xmlns="http://www.w3.org/2000/svg" width="18" viewBox="0 0 18 23" class="slice-icon-circle">
            <g fill="#D2401E">
                <path
                    d="M18 19.9c0-.1 0-.2-.1-.2 0-.1 0-.1-.1-.2 0-.1-.1-.3-.2-.6l-.3-.8c-.2-.4-.4-1.1-.6-1.5L10.4 1.2C10.3.8 9.9 0 9.1 0H9h-.1c-.8 0-1.2.8-1.3 1.2L1.3 16.6c-.2.4-.4 1.1-.6 1.5l-.3.8c-.1.3-.2.5-.2.6 0 .1-.1.1-.1.2s-.1.2-.1.3c-.1.3 0 .7.4 1.1.1 0 .1.1.2.1.1.1.3.2.5.3.2 0 2.8 1.5 7.6 1.5h.6c4.8 0 7.4-1.5 7.5-1.6.2-.1.4-.2.5-.3.1-.1.2-.1.2-.2.5-.3.5-.7.5-1zm-7.2-15l1 2.5c-.3.1-.6.2-.9 0-.3-.1-.6-.3-.8-.7-.1-.2-.2-.6-.1-.9.2-.4.4-.6.8-.9-.1.1 0 .1 0 0zM5.7 8.5c.7.4 1.3.9 1.6 1.6.3.7.3 1.6 0 2.3-.3.8-.9 1.3-1.6 1.7-.7.3-1.5.3-2.2 0l2.2-5.6zm-2.6 6.6c1 .4 2.1.4 3-.1 1-.4 1.8-1.2 2.2-2.2.4-1 .4-2.1 0-3.1-.5-1-1.2-1.7-2.2-2.1l2.4-6c.2-.3.3-.6.4-.6 0 .1.1.1.1.1s.1 0 .1-.1c.1 0 .2.2.4.6l1 2.4h-.2c-.6.3-1 .8-1.2 1.4-.3.6-.2 1.3.1 1.8.3.6.8 1 1.4 1.2.5.2 1.1.2 1.7-.1l3.5 8.6c.1.3.3.8.5 1.2h-.2c-.1 0-6.4 3.3-14.2 0h-.1c.2-.4.4-.9.5-1.2l.8-1.8zm13.2 5.4s-2.4 1.4-7 1.4h-.6c-4.6 0-7-1.4-7-1.4-.4-.2-.7-.4-.7-.4s.1-.3.3-.7l.1-.1.1.1c4.3 1.8 8.2 1.7 10.6 1.3 2.7-.4 4.4-1.3 4.4-1.4h.1l.1.1c.1.3.3.6.3.6 0 .1-.3.3-.7.5z" />
                <path
                    d="M11.2 18.4c1.1 0 2-.9 2-2s-.9-2-2-2-2 .9-2 2c.1 1.1.9 2 2 2zm0-2.9c.5 0 .9.4.9.9s-.4.9-.9.9-.9-.4-.9-.9.4-.9.9-.9z" />
            </g>
        </svg>
    </section>
</template>

<script>

    export default {
        name: 'EventsSection',

        data() {
            return {
                events: [
                    {
                        name: 'traditional neapolitan pies in kyoto pizza mercato',
                        location: '204 E. Pizzetta Tommaso',
                        day: '02',
                        month: 'nov',
                    },
                    {
                        name: 'terrazza patio dining space opening this weekend',
                        location: '204 E. Pizzetta Tommaso',
                        day: '03',
                        month: 'nov',
                    },
                    {
                        name: 'sienna private dining room with stéphane brunn',
                        location: '204 E. Pizzetta Tommaso',
                        day: '04',
                        month: 'nov',
                    },
                ]
            }
        }

    }
</script>

<style lang="scss" scoped>
    @import '../../../style/global.scss';

    #events {
        display: flex;
        align-items: center;
        height: 85vh;
        position: relative;

        .border-events {
            border-bottom: 3px dotted $bg-slider-dots;
        }

        .events-wrapper,
        .events-bg {
            width: 50%;
        }

        .events-wrapper {
            background: $bg-dark-stars;
            height: 100%;

            .events-list {
                display: flex;
                flex-direction: column;
                padding: 50px 0;
                width: 75%;
                margin: 0 auto;
                height: 90%;
                overflow-y: auto;

                &::-webkit-scrollbar{
                    display: none;
                }

                h5 {
                    color: $text-dark-primary;
                }

                h2 {
                    color: $text-events;
                    font-size: 2em;
                }

                ul {
                    list-style-type: none;
                    flex-grow: 1;

                    .single-event {
                        display: flex;
                        width: 75%;
                        padding: 30px 0;

                        .event-date {
                            text-align: center;
                            margin-right: 30px;

                            .event-day {
                                display: block;
                                color: $text-dark-primary;
                                font-size: 3em;
                                margin-bottom: -10px;
                            }

                            .event-month {
                                font-size: 1.5em;
                                color: $text-events;
                            }
                        }


                        .event-details {
                            margin-top: 15px;
                            width: 85%;
                            padding: 0 10px;

                            .event-name {
                                margin-bottom: 5px;
                                color: $text-events;
                                font-size: 1.4em;
                                width: 370px;
                            }

                            .event-location {
                                color: $text-primary;

                                span {
                                    text-transform: initial;
                                    margin-left: 10px;
                                }
                            }
                        }

                    }
                }
            }

            .bg-white {
                height: 10%;
            }
        } 

        .events-bg {
            background-image: url('../../../assets/img/h3-img-5a.jpg');
            background-size: cover;
            background-repeat: no-repeat;
            background-position: right;
            height: 100%;
        }

        .slice-icon-circle {
            top: 10px;
        }
    }
</style>