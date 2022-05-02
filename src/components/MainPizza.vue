<template>
    <main>
        <HeroSection />

        <!-- tutte le sezioni presenti in questo div hanno il bg white -->
        <div class="bg-white">
            <TestimonialsSection />
            <SpecialsSection />
            <MosaicPizza />
            <TeamSection />
            <ClientsSection />
            <MenuSection />
        </div>

        <div class="fixed-main-icons">
            <div class="cycle-icon">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 87 87" height="20px" width="20px" fill="#fff">
                    <path d="M55.4 81.5c6.1-11.1 5.2-16.1-4.3-24.3 6.1-3.5 9.5-8.5 9.1-15.7-.5-8.2-7.7-14.7-16.3-14.6-8.5.1-15.6 6.7-15.9 15-.3 8.5 5.9 15.8 14.3 16.6 1.4.1 2.8.2 4.2.5 5.9 1.2 10.2 6.7 9.8 12.6-.4 6.4-5.5 11.4-11.8 11.7-19.6.9-38.6-14.8-41.3-34C-.1 26.9 14.4 6.8 36.4 2.8c22.3-4 43.4 10 48.1 32 4.3 20-8.6 41.2-28.4 46.7h-.7z"/>
                </svg>
            </div>
            
            <div class="cart-icon bg-white">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" height="16px" width="16px" fill="#ef2853">
                    <circle cx="9" cy="21" r="2"/>
                    <circle cx="20" cy="21" r="2"/>
                    <path d="M23.8 5.4c-.2-.3-.5-.4-.8-.4H6.8L6 .8C5.9.3 5.5 0 5 0H1C.4 0 0 .4 0 1s.4 1 1 1h3.2L5 6.2v.1l1.7 8.3C7 16 8.2 17 9.6 17H19.4c1.5 0 2.7-1 3-2.4L24 6.2c0-.3 0-.6-.2-.8z"/>
                </svg>
            </div>
        </div>

        <EventsSection />
        
        <BookingSection />
        
    </main>
</template>

<script>
    import HeroSection from './partials/MainChildren/HeroSection.vue';
    import TestimonialsSection from './partials/MainChildren/TestimonialsSection.vue';
    import SpecialsSection from './partials/MainChildren/SpecialsSection.vue';
    import MosaicPizza from './partials/MainChildren/MosaicPizza.vue';
    import TeamSection from './partials/MainChildren/TeamSection.vue';
    import ClientsSection from './partials/MainChildren/ClientsSection.vue';
    import MenuSection from './partials/MainChildren/MenuSection.vue';
    import EventsSection from './partials/MainChildren/EventsSection.vue';
    import BookingSection from './partials/MainChildren/BookingSection.vue';

    export default {
        name: 'MainPizza',

        components: {
            HeroSection,
            TestimonialsSection,
            SpecialsSection,
            MosaicPizza,
            TeamSection,
            ClientsSection,
            MenuSection,
            EventsSection,
            BookingSection,
        },
    }
</script>

<style lang="scss">
    @import '../style/global.scss';

    main {
        position: relative;

        .fixed-main-icons {
            position: fixed;
            right: 0;
            top: 20%;
            z-index: 9999;

            div {
                @include compileFlex(initial, center, center);
                width: 30px;
                height: 30px;
                cursor: pointer;
            }

            .cycle-icon {
                background-color: #EF2853;
                margin-bottom: 5px;
            }
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

        a {
            color: $text-primary;
            text-decoration: none;
            position: relative;
            top: 5px;
        }
    }

    .prev {
        transform: rotate(90deg);
    }

    .next {
        transform: rotate(270deg);
    }
</style>