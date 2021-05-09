<template>
    <div>
        <b-navbar>
            <template #brand>
                <b-navbar-item tag="router-link" :to="{ path: '/' }">
                    <img
                        src="https://raw.githubusercontent.com/buefy/buefy/dev/static/img/buefy-logo.png"
                        alt="Lightweight UI components for Vue.js based on Bulma"
                    >
                </b-navbar-item>
            </template>

            <template #end>
                <b-navbar-item tag="div">
                    <div class="buttons">
                        <a href="/register" class="button is-primary navbar_buttons">
                            <strong>Inscription</strong>
                        </a>
                        <a href="/login" class="button is-light navbar_buttons">
                            Connexion
                        </a>
                    </div>
                </b-navbar-item>
            </template>
        </b-navbar>
    </div>
</template>

<style scoped>
.navbar_buttons{
    border-radius : 50px;
}
</style>