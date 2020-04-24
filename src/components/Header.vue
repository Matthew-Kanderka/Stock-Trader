<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <router-link class="navbar-brand" to="/">Stock Trader</router-link>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav mr-auto">
                <li class="nav-item">
                    <router-link to="/portfolio"><a class="nav-link" href="#">Portfolio</a></router-link>
                </li>
                <li class="nav-item">
                    <router-link to="/stocks"><a class="nav-link" href="#">Stocks</a></router-link>
                </li>
            </ul>
            <ul class="navbar-nav">
                <li class="nav-item">
                    <a class="nav-link" href="#" @click="endDay">End Day</a>
                </li>
                <li class="nav-item dropdown" :class="{show: isDropdownOpen}" @click="isDropdownOpen = !isDropdownOpen">
                    <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                        Save & Load
                    </a>
                    <div class="dropdown-menu" :class="{show: isDropdownOpen}" aria-labelledby="navbarDropdown">
                        <a class="dropdown-item" href="#">Save Data</a>
                        <a class="dropdown-item" href="#">Load Data</a>
                    </div>
                </li>
            </ul>
            <strong class="navbar-nav">Funds: {{ funds | currency }}</strong>
        </div>
    </nav>
</template>

<script>
    import {mapActions} from 'vuex'

    export default {
        name: "Header",
        data() {
            return {
                isDropdownOpen: false
            }
        },
        computed: {
            funds() {
                return this.$store.getters.funds;
            }
        },
        methods: {
            ...mapActions([
                'randomizeStocks'
            ]),
            endDay() {
                this.randomizeStocks();
            }
        }
    }
</script>

<style scoped>

</style>