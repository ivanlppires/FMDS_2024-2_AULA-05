<template>
    <v-list>
        <v-list-subheader>
            {{ titulo }}
        </v-list-subheader>
        <v-list-item prepend-icon="mdi-home" to="/" title="Início" />
        <v-list-item prepend-icon="mdi-whatsapp" to="/Contato" title="Contato" />
        <v-list-item prepend-icon="mdi-account" to="/MinhaConta" title="Minha conta" />
        <v-list-item prepend-icon="mdi-file-document" to="/Relatorio" title="Relatórios" />
    </v-list>
    <v-divider></v-divider>
    <v-btn block color="primary" @click="$emit('logout')">
        Logout
    </v-btn>
</template>

<script setup>
const props = defineProps({
    titulo: String,
});
</script>