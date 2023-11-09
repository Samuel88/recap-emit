<script>
export default {
    emits: ['notifySend'],
    data() {
        return {
            testo: ''
        }
    },
    methods: {
        inviaNotifica() {
            this.$emit('notifySend', {
                testo: this.testo
            });
            this.testo = '';
        }
    }
}
</script>
<template>
    <input @keyup.enter="inviaNotifica()" type="text" v-model="testo">
    <button @click="inviaNotifica()">Invia Notifica</button>
</template>