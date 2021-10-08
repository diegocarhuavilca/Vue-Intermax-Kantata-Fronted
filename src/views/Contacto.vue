<template>
    <div class="container formulario my-5 p-5" v-if="!enviado">
        <div class="container my-3 p-2" style="background-color:rgba(0,48,110,255)">
            <h1 class="text-white">Contactanos</h1>
        </div>

        <div class="container">
            <form @submit.prevent="enviarFomulario">
                <div class="container w-50 d-flex align-items-center">
                    <div class="container d-flex flex-column">
                        <label for="nombre">Nombre</label>
                        <input type="text" id="nombre" name="nombre" v-model="Nombre" required />
                    </div>
                    <div class="container d-flex flex-column">
                        <label for="apellido">Apellido</label>
                        <input
                            type="text"
                            id="Apellido"
                            name="Apellido"
                            v-model="Apellido"
                            required
                        />
                    </div>
                </div>

                <div class="container w-50 d-flex align-items-center">
                    <div class="container d-flex flex-column">
                        <label for="email">E-mail</label>
                        <input type="email" id="email" name="email" v-model="Email" required />
                    </div>
                    <div class="container d-flex flex-column">
                        <label for="telefono">Telefono</label>
                        <input
                            type="text"
                            id="telefono"
                            name="telefono"
                            v-model="Telefono"
                            required
                        />
                    </div>
                </div>
                <div class="container w-50 d-flex flex-column align-items-center mt-3">
                    <label for="mensaje">Mensaje</label>
                    <textarea
                        name="mensaje"
                        rows="5"
                        class="w-100"
                        style="resize:none"
                        required
                        v-model="Mensaje"
                    ></textarea>
                </div>
                <button
                    type="submit"
                    class="btn btn-primary m-3"
                    style="background-color:#00b6dc;color :white"
                >Enviar</button>
            </form>
        </div>
    </div>
    <div class v-else>
        <h1 style="font-weight:bold">Hemos Recibido su Mensaje</h1>
        <h3>En breve nos contacteremos con ud</h3>
    </div>
</template>

<script>
import axios from "axios";
export default {
    setup() {
        return {};
    },
    data() {
        return {
            Nombre: "",
            Apellido: "",
            Email: "",
            Telefono: "",
            Mensaje: "",
            enviado: false,
        };
    },
    methods: {
        enviarFomulario() {
            axios
                .post("http://localhost:1337/contactos", {
                    Nombre: this.Nombre,
                    Apellido: this.Apellido,
                    Email: this.Email,
                    Telefono: this.Telefono,
                    Mensaje: this.Mensaje,
                })
                .then(() => {
                    this.enviado = true;
                })
                .catch((error) => {
                    alert(error);
                });
        },
    },
};
</script>

<style lang="scss" scoped>
h1 {
    display: inline-block;
}
button {
    border: none;
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}

/* Firefox */
input[type="number"] {
    -moz-appearance: textfield;
}
</style>