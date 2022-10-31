<template>
    <div class="row">
        <q-form @submit.prevent="submit">
            <h1>Login Cliente</h1>
            <div class="col-12">
                <q-input outlined v-model="form.cpf" label="CPF" mask="###.###.###-##" />
            </div>
            <div class="col-12">
                <q-input outlined v-model="form.senha" label="Senha" :type="isPwd ? 'password' : 'text'">
                    <template v-slot:append>
                        <q-icon
                            :name="isPwd ? 'visibility_off' : 'visibility'"
                            class="cursor-pointer"
                            @click="isPwd = !isPwd"
                        />
                    </template>
                </q-input>
            </div>
            <div class="col-12">
                <q-btn type="submit">Logar</q-btn>
            </div>
        </q-form>
    </div>
</template>

<script>
import {mapActions} from 'vuex';

export default ({
    name: "loginCliente",
    data() {
        return {
            form: {
                cpf: "",
                senha: "",
            },
            isPwd: true,
        }
    },
    methods: {
        ...mapActions('cliente', ['ActionClienteLogin']),
        async submit() {
            await this.ActionClienteLogin(this.form);
            this.clear()
            this.$router.push('cliente/mapa')
        },
        clear() {
            this.form = {
                cpf: "",
                senha: "",
            } 
        }
    }
})
</script>
