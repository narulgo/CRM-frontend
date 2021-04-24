<template>
    <nav class="navbar is-dark">
        <div class="navbar-brand">
            <router-link to="/" class="navbar-item">
                <strong>CRM</strong>
            </router-link>
        </div>

        <div class="navbar-menu">
            <div class="navbar-end">
                <router-link to="/dashboard/leads" class="navbar-item">Leads</router-link>
                <div class="navbar-item">
                    <div class="buttons">
                        <div v-if="isAuthenticated">
                            <router-link to="/dashboard/account" class="button is-info">My account</router-link>
                        </div>
                        <div v-else>
                            <router-link to="/sign-up" class="button is-success"><strong>Sign up</strong></router-link>
                            <router-link to="/log-in" class="button is-light">Log in</router-link>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>

<script>
import { mapState } from 'vuex'
export default {
    name: 'Navbar',
    computed: {
        ...mapState(['isAuthenticated'])
    }
}
</script>
