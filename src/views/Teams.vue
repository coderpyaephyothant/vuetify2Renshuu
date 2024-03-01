<template>
<div>
  <h3 class="grey--text">Teams</h3>
  <v-container fluid>
    <v-row>
      <v-col 
      cols="12" 
      sm="6"
      md="4"
      lg="3"
      v-for="team in teams"
      :key="team.id"
      >
        <v-card
         class="text-center"
         >
         <v-responsive>
          <v-avatar
            color="warning lighten-2"
            size="100"
          >
          <img
        :src="team.avator"
      ></v-avatar>
         </v-responsive>
         <v-card-text>
          <div>{{team.name}}</div>
          <div class="grey--text">{{team.rolw}}</div>
         </v-card-text>
         <v-card-actions>
              <v-btn
                color="grey"
                text
                flat
          >
                <v-icon class="mdi mdi-message" small ></v-icon>
                <span class="grey--text">Message</span>
              </v-btn>
         </v-card-actions>
         </v-card>
      </v-col>
    </v-row>
  </v-container>
</div >
</template>

<script>
export default {
  data(){
    return {
      teams:[
        {id:1, name:'Pyae Phyo Thant', role:'Frontend Developer',avator:'/avatar-1.png'},
        {id:2, name:'Ko Phoe Ngal', role:'Senior Backend Developer',avator:'/avatar-2.png'},
        {id:3, name:'PaingZay', role:'FullStack Developer',avator:'/avatar-3.png'},
        {id:4, name:'Ko Thein Min Swe', role:'Senior Developer',avator:'/avatar-4.png'},
        {id:4, name:'Ko Kyaw Thet Aung', role:'Senior Backend Developer',avator:'/avatar-5.png'},
      ]
    }
  }
}
</script>

<style>

</style>
