<template>
    <div class="ventana-chat">
        <div class="mensajes">
            <div v-for="(mensaje, indice) in mensajes" :key="indice" :class="['mensaje', mensaje.remitente]" :style="{ backgroundColor: mensaje.color }">
                <strong>{{ mensaje.nombreUsuario }}</strong>
                <p>{{ mensaje.texto }}</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'VentanaChat',
    props: {
        mensajes: {
            type: Array,
            required: true,
            default: () => [],
        },
    },
};
</script>

<style scoped>
.ventana-chat {
    flex: 3;
    border: 1px solid #ccc;
    border-radius: 8px;
    background: white;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    height: 100%;
    min-width: 500px;
    display: flex;
    flex-direction: column;
}

.mensajes {
    flex: 1;
    padding: 20px;
    overflow-y: auto;
    display: flex;
    flex-direction: column;
    gap: 15px;
    scroll-behavior: smooth;
}

.mensaje {
    padding: 12px 15px;
    border-radius: 12px;
    max-width: 70%;
    word-wrap: break-word;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
}

.mensaje strong {
    display: block;
    margin-bottom: 5px;
    font-size: 0.9em;
    color: #333;
}

.mensaje p {
    margin: 0;
    font-size: 1em;
    line-height: 1.4;
}

.izquierda {
    align-self: flex-start;
    border-bottom-left-radius: 4px;
    margin-right: auto;
}

.derecha {
    align-self: flex-end;
    border-bottom-right-radius: 4px;
    margin-left: auto;
}

/* Para el scroll personalizado */
.mensajes::-webkit-scrollbar {
    width: 8px;
}

.mensajes::-webkit-scrollbar-track {
    background: #f1f1f1;
    border-radius: 4px;
}

.mensajes::-webkit-scrollbar-thumb {
    background: #888;
    border-radius: 4px;
}

.mensajes::-webkit-scrollbar-thumb:hover {
    background: #555;
}
</style>
