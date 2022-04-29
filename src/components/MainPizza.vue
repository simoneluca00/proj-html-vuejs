<template>
    <main>
        <HeroSection />

        <!-- tutte le sezioni presenti in questo div hanno il bg white -->
        <div class="bg-white">
            <TestimonialsSection />
            <SpecialsSection />
        </div>
    </main>
</template>

<script>
    import HeroSection from './partials/MainChildren/HeroSection.vue';
    import TestimonialsSection from './partials/MainChildren/TestimonialsSection.vue';
    import SpecialsSection from './partials/MainChildren/SpecialsSection.vue';

    export default {
        name: 'MainPizza',

        components: {
            HeroSection,
            TestimonialsSection,
            SpecialsSection,
        },
    }
</script>

<style lang="scss">
    @import '../style/global.scss';

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
        left: -10px;
        transform: rotate(90deg);
    }

    .next {
        right: -10px;
        transform: rotate(270deg);
    }
</style>