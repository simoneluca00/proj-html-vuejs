<template>
    <main>
        <HeroSection />
        
        <!-- tutte le sezioni presenti in questo div hanno il bg white -->
        <div class="bg-white">

        </div>
    </main>
</template>

<script>
    import HeroSection from './partials/MainChildren/HeroSection.vue'

    export default {
        name: 'MainPizza',

        components: {
            HeroSection,
        },
    }
</script>

<style lang="scss">
    @import '../style/global.scss';
</style>