<template>
    <nav class="navbar container" role="navigation" aria-label="main navigation">
        <div class="navbar-brand">
            <a class="navbar-item" href="/">
                <strong class="is-size-4">SATFX</strong>
            </a>
            <a role="button" class="navbar-burger burger" aria-label="menu" aria-expanded="false"
               data-target="navbarBasicExample">
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
                <span aria-hidden="true"></span>
            </a>
        </div>
        <div id="navbar" class="navbar-menu">
            <div class="navbar-start">
                <router-link to="/" class="navbar-item">Home</router-link>
                <router-link to="/about" class="navbar-item">About</router-link>
            </div>
            <div class="navbar-end">
                <div class="navbar-item">
                    <div class="buttons">
                        <a href="/login" role="button" class="button is-dark" v-if="!user">
                            <strong>Sign in</strong>
                        </a>
                        <a href="/" role="button" class="button is-dark" @click="$emit('logout')" v-if="user">
                            <strong>Sign Out</strong>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>
<script>
    export default {
        name: 'Nav',
        props: ["user"]
    }
</script>
<style lang="scss" scoped>
    nav {
        margin-top: 25px;
        margin-bottom: 30px;

        a {
            font-weight: bold;
            color: #2c3e50;

            &.router-link-exact-active {
                color: #d88d00;
            }
        }
    }
</style>