<template>
    <div class="container is-widescreen">
        <div class="columns is-vcentered">
            <div class="column">
                <img class="login_picture" src="../assets/register.svg">
            </div>
            <div class="column">
                <section class="hero">
                    <div class="hero-body">
                        <p class="title has-text-primary">
                        Inscription
                        </p>
                    </div>
                </section>
                <form action="">
                    <b-field label="Pseudo">
                        <b-input rounded v-model="pseudo"></b-input>
                        <p v-if="errors.pseudo" class="mt-2 has-text-danger">{{errors.pseudo}}</p>
                    </b-field>

                    <b-field label="Email">
                        <b-input rounded v-model="email"></b-input>
                        <p v-if="errors.email" class="mt-2 has-text-danger">{{errors.email}}</p>
                    </b-field>

                    <div class="columns">
                        <div class="column">
                            <b-field label="Mot de passe">
                                <b-input type="password" rounded v-model="password"></b-input>
                                <p v-if="errors.password" class="mt-2 has-text-danger">{{errors.password}}</p>
                            </b-field>
                        </div>
                        <div class="column">
                            <b-field label="Confirmation mot de passe">
                                <b-input type="password" rounded v-model="password_confirm"></b-input>
                                <p v-if="errors.password" class="mt-2 has-text-danger">{{errors.password_confirm}}</p>
                            </b-field>
                        </div>
                    </div>

                    <b-button class="mt-5" type="is-primary" expanded rounded @click="register">S'inscrire</b-button>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                pseudo : null,
                email: null,
                password : null,
                password_confirm : null,
                errors : {}
            }
        },
        methods: {
            register() {
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