<template>
    <nav>
        <!-- componente per NAV menù sinistro -->
        <NavLeftMenu />

        <!-- componente LOGO al centro tra i due menu -->
        <LogoPizza />

        <!-- componente per NAV menù destro -->
        <NavRightMenu />
    </nav>
</template>

<script>
    import NavLeftMenu from './partials/HeaderChildren/NavLeftMenu.vue'
    import NavRightMenu from './partials/HeaderChildren/NavRightMenu.vue'
    import LogoPizza from './partials/HeaderChildren/LogoPizza.vue'

    export default {
        name: 'HeaderPizza',

        components: {
            NavLeftMenu,
            NavRightMenu,
            LogoPizza,
        },

    }
</script>

<style lang="scss">
    @import '@/style/global.scss';

    nav,
    .menu,
    ul.links {
        @include compileFlex(nowrap, space-between, center);
    }

    nav {
        height: 100%;
        width: 80%;
        margin: 0 auto;
        color: $white;

        li {
            display: flex;
            align-items: center;

            a {
                color: $white;
                font-size: 0.9em;
            }
        }

    }
</style>