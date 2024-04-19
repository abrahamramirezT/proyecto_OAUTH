<template>
    <div class="home" style="background-color: #f0f4f8; padding: 20px; border-radius: 8px; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);">
        <h1 style="color: #333; font-family: 'Arial', sans-serif; text-align: center;">Login con OAuth</h1>
        <!-- Revisa si la librería está cargando antes de mostrar los botones de acceso -->
        <div v-if="!$auth.loading" style="display: flex; justify-content: center; gap: 10px; padding-top: 20px;">
            <!-- Muestra el botón de login si no está autentificado -->
            <b-button variant="outline-secondary" v-if="!$auth.isAuthenticated" @click="login" style="border-color: #007BFF; color: #007BFF;">Iniciar Sesión</b-button>
            <!-- Muestra el botón de logout si está autentificado -->
            <b-button variant="outline-danger" v-if="$auth.isAuthenticated" @click="logout" style="border-color: #FF073A; color: #FF073A;">Cerrar Sesión</b-button>
        </div>
    </div>
</template>

<script>
export default {
    name: "home",
    methods: {
        login() {
            this.$auth.loginWithRedirect();
        },
        logout() {
            this.$auth.logout({
                logoutParams: {
                    returnTo: window.location.origin,
                },
            });
        },
    },
};
</script>

