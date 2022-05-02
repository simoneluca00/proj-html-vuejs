<template>
    <section id="booking" class="bg-white">
        <div class="main-container">
            <div class="centred">
                <div class="number-booking">
                    <!-- pseudo-icona per input number -->
                    <img src="../../../assets/img/users-icon.png" alt="users icon">
                    <input type="number" placeholder="1 Person" min="1">
                </div>

                <span class="text-divisor">for</span>

                <input type="date" value="2022-05-03">

                <span class="text-divisor">at</span>

                <input type="time" id="appt" name="appt" min="11:00" max="22:00" value="19:00" required>

                <button class="btn btn-primary">book a table</button>
            </div>

            <span class="credits fw-300">*Powered by OpenTable </span>
        </div>
    </section>
</template>

<script>

    export default {
        name: 'BookingSection',

        data() {
            return {

            }
        }

    }
</script>

<style lang="scss" scoped>
    @import '../../../style/global.scss';

    #booking {
        height: 30vh;
        padding: 5px 0;

        .main-container {
            @include compileFlex(initial, center, center);
            flex-direction: column;
            background-image: url('../../../assets/img/h3-background-img-3.jpg');
            background-size: cover;
            background-position: right;
            height: 100%;

            .centred {
                @include compileFlex(nowrap, space-around, center);
                height: 50px;
                width: 70%;
                margin-bottom: 5px;

                .number-booking {
                    position: relative;

                    img {
                        position: absolute;
                        right: 15px;
                        top: 25%;
                        width: 23px;
                    }
                }

                input,
                button,
                .number-booking {
                    width: 20%;
                    height: 100%;
                }

                input {
                    padding: 0 15px;
                    text-transform: capitalize;
                    color: $text-input;
                    font-family: sans-serif;
                    outline: none;
                    border: 1.5px solid #1F1F1F;


                    &::placeholder {
                        color: $text-input;
                        font-family: sans-serif;
                    }

                    &[type=number] {
                        width: 100%;
                    }

                    &[type=date]::-webkit-calendar-picker-indicator,
                    &[type=time]::-webkit-calendar-picker-indicator {
                        background-size: 170%;
                        background-position: center;
                        cursor: pointer;
                    }

                    &[type=date]::-webkit-calendar-picker-indicator {
                        background-image: url('../../../assets/img/calendar-icon.png');
                    }

                    &[type=time]::-webkit-calendar-picker-indicator {
                        background-image: url('../../../assets/img/clock-icon.png');
                    }

                    &[type=number]::-webkit-inner-spin-button {
                        display: none;
                    }

                }

                span.text-divisor {
                    color: $white;
                    margin: 0 -40px;
                }

            }

            span.credits {
                width: 66%;
                color: $white;
                text-transform: initial;
                font-size: 0.8em;
                font-family: sans-serif;
                letter-spacing: initial;
            }
        }
    }
</style>