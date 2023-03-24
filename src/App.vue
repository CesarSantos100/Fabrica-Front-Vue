<template>
  <v-app id="inspire">

    <v-navigation-drawer
      v-model="drawer"
      app
    >
    <v-list dense>
      <v-list-item link :to="item.rota" v-for="(item, index) in rotas" :key="index">
        <v-list-item-action>
          <v-icon>{{ item.icone }}</v-icon>
        </v-list-item-action>
        <v-list-item-content>
            <v-list-item-title>{{ item.nome }}</v-list-item-title>
            </v-list-item-content> 
      </v-list-item>
      
    </v-list>


      <!--  -->
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>Application</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <v-container>
        <router-view></router-view>
      </v-container>
    </v-main>
<v-footer color="indingo" app>
  <span class="white--text"
    >Fabrica Online - High Tech &copy; {{ new Date().getFullYear() }}</span>
</v-footer>

  </v-app>
</template>

<script>
  export default {
    data: () => ({ 
      drawer: null,
      rotas: [
        {
          nome:"Home",
          icone:"mdi-home",
          rota: "/"
        },
        {
          nome:"Contas",
          icone:"mdi-cash",
          rota: "/Contas"
        },
        {
          nome:"Usuarios",
          icone:"mdi-account",
          rota: "/Usuarios"
        },
        {
          nome:"Relatorios",
          icone:"mdi-align-vertical-bottom",
          rota: "/Relatorios"
        },
      ]
    })
  }
</script>
