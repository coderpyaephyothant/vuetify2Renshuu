<template>
    <nav>
      <!-- snackBar -->
         <v-snackbar
      v-model="snackbar"
      color="success"
      :timeout="timeout"
      :vertical="true"
    >
      {{ text }}
    </v-snackbar>

    <v-app-bar flat app class="">
        <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer">
        </v-app-bar-nav-icon>
        <v-toolbar-title class="text-uppercase grey--text">
            <span class="font-weight-light">Vuetify</span>
            <span>Rush</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>

<!-- Menu Component -->

         <v-menu offset-y>
      <template v-slot:activator="{ on, attrs }">
        <v-btn
          v-bind="attrs"
          v-on="on"
          depressed
          
        >
        <v-icon small left class="grey--text">mdi mdi-chevron-down</v-icon>
          <span class="grey--text">Menu</span>
        </v-btn>
      </template>
      <v-list>
        <v-list-item
        v-for="menu in menus" :key="menu.id" :to="menu.route"
        >
          <v-list-item-title>{{menu.title}}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu>
        <v-btn depressed>
            <span>サインアウト</span>
            <v-icon right>mdi-exit-to-app</v-icon>
        </v-btn>
    </v-app-bar>
    
    <v-navigation-drawer 
     app v-model="drawer"
     class="grey-lighten-4" 
     color="#5500ffa7"
      >
      <v-row class="mt-2">
        <v-col class="">
                <div class="text-center">
                    <v-avatar>
                        <img src="/avatar-1.png" alt="">
                    </v-avatar>
                    <p class="white--text">Pyae Phyo Thant</p>
                    <Dialog @successfullyCreated="showMessage"/>
                </div>
        </v-col>
      </v-row>
        <v-list class="white--text">
      <v-list-item-group
        mandatory
        class=""
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
import Dialog from './Dialog.vue'
export default {
  components:{
    Dialog
  },
    data(){
        return {
            drawer:true,
            menus:[
                {id:1, title:'Dashboard', icon:'mdi mdi-view-dashboard', route:'/'},
                {id:2, title:'Projects',icon:'mdi mdi-folder', route:'/projects'},
                {id:3, title:'Team',icon:'mdi mdi-account-multiple-outline', route:'/teams'},
            ],
            snackbar:true,
            text:'Vuetify UI で作りました。',
            timeout:2000
        }
    },
    methods:{
      showMessage(updatedText){
        this.snackbar = true
        this.text = updatedText
      }
    }
}
</script>

<style>

</style>