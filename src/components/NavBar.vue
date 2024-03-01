<template>
    <nav>
    <v-app-bar flat app class="">
        <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer">
        </v-app-bar-nav-icon>
        <v-toolbar-title class="text-uppercase grey--text">
            <span class="font-weight-light">Vuetify</span>
            <span>Rush</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn depressed>
            <span>サインアウト</span>
            <v-icon right>mdi-exit-to-app</v-icon>
        </v-btn>
    </v-app-bar>
    
    <v-navigation-drawer app v-model="drawer" class="grey-lighten-4" >
        <v-list>
      <v-list-item-group
        mandatory
        color="green"
      >
            <v-list-item v-for="menu in menus" :key="menu.id" :to="menu.route" >
            <v-list-item-icon>
                <v-icon>
                    {{menu.icon}}
                </v-icon>
            </v-list-item-icon>
            <v-list-item-content>
                <v-list-item-title>
                    {{menu.title}}
                </v-list-item-title>
            </v-list-item-content>
            </v-list-item>
      </v-list-item-group>
    </v-list>
    </v-navigation-drawer>
    </nav>
</template>

<script>
export default {
    data(){
        return {
            drawer:true,
            menus:[
                {id:1, title:'Dashboard', icon:'mdi mdi-view-dashboard', route:'/'},
                {id:2, title:'Projects',icon:'mdi mdi-folder', route:'/projects'},
                {id:3, title:'Team',icon:'mdi mdi-account-multiple-outline', route:'/teams'},
            ]
        }
    }
}
</script>

<style>

</style>