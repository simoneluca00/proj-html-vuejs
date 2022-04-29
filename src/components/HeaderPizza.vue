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
    @import '../style/global.scss';

    nav {
        @include compileFlex(nowrap, space-between, center);
        height: 100%;
        width: 80%;
        margin: 0 auto;
        color: $white;

        .menu {
            @include compileFlex(nowrap, space-between, center);

            ul.links {
                @include compileFlex(nowrap, space-between, center);
                list-style-type: none;
            }
                li {
                    @include compileFlex(nowrap, initial, center);

                    a {
                        text-decoration: none;
                        color: $white;
                        font-size: 0.9em;
                    }
                }

        }
    }
</style>