<template>
    <main>
        <HeroSection />

        <!-- tutte le sezioni presenti in questo div hanno il bg white -->
        <div class="bg-white">
            <TestimonialsSection />
            <SpecialsSection />
            <MosaicPizza />
            <TeamSection />
        </div>
    </main>
</template>

<script>
    import HeroSection from './partials/MainChildren/HeroSection.vue';
    import TestimonialsSection from './partials/MainChildren/TestimonialsSection.vue';
    import SpecialsSection from './partials/MainChildren/SpecialsSection.vue';
    import MosaicPizza from './partials/MainChildren/MosaicPizza.vue';
    import TeamSection from './partials/MainChildren/TeamSection.vue';

    export default {
        name: 'MainPizza',

        components: {
            HeroSection,
            TestimonialsSection,
            SpecialsSection,
            MosaicPizza,
            TeamSection,
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
        transform: rotate(90deg);
    }

    .next {
        transform: rotate(270deg);
    }
</style>