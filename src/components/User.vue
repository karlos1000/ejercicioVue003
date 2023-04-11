<template>
    <div v-show="option_user">
        <div>
            <label>Nombre:</label>
            <input type="text" v-model="user">
        </div>
        <div>
            <label>Apellido:</label>
            <input type="text" v-model="lastname">
        </div>
        <div>
            <button v-on:click="send">Enviar</button>
        </div>
    </div>

    <div v-show="option_b">
        Bienvenido
        <div>Nombre: {{ user }}</div>
        <div>Apellido: {{ lastname }}</div>
    </div>
</template>

<script>
import {ref} from "vue";
export default {
    name: 'User',
    props: {
    },
    setup() {
        let user = ref("");
        let lastname = ref("");
        let option_user = ref(true);
        let option_b = ref(false);

        const send = () => {
            option_user.value = false;
            option_b.value = true;
            console.log("send", user.value, lastname.value);
        }

        return {
            user,
            lastname,
            option_user,
            option_b,
            send,
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
