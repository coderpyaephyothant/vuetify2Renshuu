<template>
<div>
  <h3 class="grey--text">Dashboard</h3>
  <v-container fluid>
    <h3>fluid</h3>

    <v-row>
      <v-col
        cols="12"
        sm="12"
        md="6"
      >
        <v-btn class="col-12">1</v-btn>
      </v-col>
      <v-col
        cols="12"
        sm="4"
        md="2"
      >
        <v-btn  class="col-12">2</v-btn>
      </v-col>
      <v-col
        cols="12"
        sm="4"
        md="2"
      >
        <v-btn  class="col-12">3</v-btn>
      </v-col>
      <v-col
        cols="12"
        sm="4"
        md="2"
      >
        <v-btn  class="col-12">4</v-btn>
      </v-col>
    </v-row>
    
    <v-row
    justify="space-around"
      >
        <v-col
        cols="12"
        sm="3"
        md="2"
         >
        <v-btn  class="col-12">5</v-btn>
        </v-col>
        <v-col
        cols="12"
        sm="3"
        md="2"
         >
        <v-btn  class="col-12">6</v-btn>
        </v-col>
      </v-row>
  </v-container>
</div> 
</template>

<script>

  export default {
    name: 'Home',

    components: {
    },
  }
</script>
