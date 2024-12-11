<template>
    <div class="contenedor-chat">
        <Usuario posicion="izquierda" :datosUsuario="usuarios[0]" @enviar-mensaje="manejarNuevoMensaje" />
        <VentanaChat :mensajes="mensajes" />
        <Usuario posicion="derecha" :datosUsuario="usuarios[1]" @enviar-mensaje="manejarNuevoMensaje" />
    </div>
</template>

<script>
import Usuario from './components/Usuario.vue';
import VentanaChat from './components/VentanaChat.vue';
import axios from 'axios';

export default {
    name: 'App',
    components: {
        Usuario,
        VentanaChat,
    },
    data() {
        return {
            mensajes: [],
            usuarios: [],
        };
    },
    async created() {
        try {
            const respuesta = await axios.get('https://randomuser.me/api/?results=2');
            this.usuarios = respuesta.data.results;
        } catch (error) {
            console.error('Error al obtener usuarios:', error);
        }
    },
    methods: {
        manejarNuevoMensaje(mensaje) {
            this.mensajes.push(mensaje);
        },
    },
};
</script>

<style scoped>
.contenedor-chat {
    display: flex;
    justify-content: space-between;
    gap: 20px;
    padding: 20px;
    max-width: 1200px;
    margin: 0 auto;
    height: 90vh;
    background-color: #f5f5f5;
}
</style>
