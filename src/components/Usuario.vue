<template>
    <div class="panel-usuario">
        <div class="info-usuario">
            <img :src="datosUsuario.picture.medium" alt="Avatar usuario" class="avatar" />
            <h3>{{ datosUsuario.name.first }}</h3>
        </div>
        <div class="entrada-mensaje">
            <input type="text" v-model="mensaje" placeholder="Escriba un mensaje..." />
            <input type="color" v-model="colorSeleccionado" />
            <button @click="enviarMensaje">Enviar</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Usuario',
    props: {
        posicion: {
            type: String,
            required: true,
        },
        datosUsuario: {
            type: Object,
            default: () => ({
                picture: { medium: '' },
                name: { first: 'Usuario' },
            }),
        },
    },
    data() {
        return {
            mensaje: '',
            colorSeleccionado: '#e0e0e0',
        };
    },
    methods: {
        enviarMensaje() {
            this.$emit('enviar-mensaje', {
                texto: this.mensaje,
                color: this.colorSeleccionado,
                remitente: this.posicion,
                nombreUsuario: this.datosUsuario.name.first,
            });
            this.mensaje = '';
        },
    },
};
</script>
<style scoped>
.panel-usuario {
    flex: 1;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 8px;
    background: white;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.info-usuario {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-bottom: 20px;
}

.avatar {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    margin-bottom: 10px;
    border: 3px solid #fff;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.entrada-mensaje {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

input[type='text'] {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    font-size: 14px;
}

input[type='color'] {
    width: 100%;
    height: 40px;
    border: 1px solid #ccc;
    border-radius: 4px;
    padding: 2px;
}

button {
    padding: 10px 20px;
    background-color: #4caf50;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 14px;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #45a049;
}

h3 {
    margin: 10px 0;
    color: #333;
    font-size: 18px;
}
</style>
