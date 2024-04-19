<template>
  <b-container id="app" fluid>
    <b-row>
      <b-col>
        <b-navbar toggleable="lg" type="light" variant="light">
          <b-navbar-brand>
            <b-link :to="{ name: 'home' }" class="navbar-link">Inicio</b-link>
          </b-navbar-brand>
          <b-navbar-toggle target="navbar-nav"></b-navbar-toggle>
          <b-collapse id="navbar-nav" is-nav>
            <b-navbar-nav class="ml-auto">
              <b-nav-item>
                <b-link v-if="$auth.isAuthenticated" :to="{ name: 'profile' }" class="navbar-link">Perfil</b-link>
              </b-nav-item>
            </b-navbar-nav>
          </b-collapse>
        </b-navbar>
      </b-col>
    </b-row>
    <b-row>
      <b-col md="9">
        <router-view/>
      </b-col>
    </b-row>
  </b-container>
</template>

<script></script>

<style scoped>
.navbar-link {
  color: #4A90E2; /* Color azul claro */
  font-weight: bold;
  transition: color 0.3s ease;
}

.navbar-link:hover {
  color: #0056b3; /* Color azul más oscuro al hacer hover */
  text-decoration: none;
}
</style>