<template>
    <div class="container is-widescreen">
        <div class="columns is-vcentered">
            <div class="column">
                <img class="login_picture" src="../assets/login.svg">
            </div>
            <div class="column">
                <section class="hero">
                    <div class="hero-body">
                        <p class="title has-text-primary">
                        Connexion
                        </p>
                    </div>
                </section>
                <form action="">
                    <b-field label="Email">
                        <b-input rounded v-model="email"></b-input>
                        <p v-if="errors.email" class="mt-2 has-text-danger">{{errors.email}}</p>
                    </b-field>
                    <b-field label="Mot de passe">
                        <b-input type="password" rounded v-model="password"></b-input>
                        <p v-if="errors.password" class="mt-2 has-text-danger">{{errors.password}}</p>
                    </b-field>

                    <b-button class="mt-5" type="is-primary" expanded rounded @click="login">Se connecter</b-button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                email: null,
                password : null,
                errors : {}
            }
        },
        methods: {
            login() {
                this.errors = {}

                if(!this.email){
                    this.$set(this.errors, 'email', 'Vous avez oublié de saisir une adresse email')
                }

                if(!this.password) {
                    this.$set(this.errors, 'password', 'Veuillez saisir un mot de passe')
                }
            }
        },
    }
</script>

<style scoped>
.login_picture{
    height: 400px;
    width: auto;
}
</style>