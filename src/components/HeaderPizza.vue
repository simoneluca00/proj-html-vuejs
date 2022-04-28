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
    import NavLeftMenu from './partials/NavLeftMenu.vue'
    import NavRightMenu from './partials/NavRightMenu.vue'
    import LogoPizza from './partials/LogoPizza.vue'

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
            // width: 38%;

            ul.links {
                @include compileFlex(nowrap, space-between, center);
                list-style-type: none;
                // width: 40%;
            }
                li {
                    @include compileFlex(nowrap, initial, center);

                    a {
                        text-decoration: none;
                        color: $white;
                    }
                }

        }
    }
</style>