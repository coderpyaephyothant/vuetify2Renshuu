<template>
  <v-dialog
  width="700"
  >
    <template v-slot:activator="{ on:dialogOn, attrs: dialogAttrs }">
        <v-tooltip bottom>
      <template v-slot:activator="{ on:tooltipOn, attrs:tooltipAttrs }">
        <div
        v-bind="tooltipAttrs"
        v-on="tooltipOn">
        <v-btn
          v-bind="dialogAttrs"
          v-on="dialogOn"
          depressed
          small
        >
        + New Project
        </v-btn>
        </div>
    </template>
    <span class="green--text">Create Project</span>
    </v-tooltip>

    </template>
    <v-card>
        <v-card-title>
            Create Project
        </v-card-title>
        <v-card-text>
            <v-form>
              <v-text-field
                v-model="title"
                label="Title"
                prepend-icon="mdi mdi-pen"
              ></v-text-field>
                <v-textarea
                name="input-7-1"
                label="Content"
                prepend-icon="mdi mdi-text"
                v-model="content"      
                ></v-textarea>
                <!-- Date Picker -->
                <v-menu
            >
          <template v-slot:activator="{ on, attrs }">
            <v-text-field
              clearable
              label="Due Date"
              readonly
              v-model="formattedDate"
              v-bind="attrs"
              v-on="on"
            ></v-text-field>
          </template>
          <v-date-picker
            v-model="date"
          ></v-date-picker>
        </v-menu>
                <!-- Button -->
                <v-btn class="success mt-2 mx-0" depressed small @click="submit()">Submit</v-btn>
            </v-form>
        </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
import format from 'date-fns/format'
export default {
data (){
  return {
    title:'',
    content:'',
    date:null
  }
},
computed:{
  formattedDate (){
    return this.date? format(this.date, 'MMMM dd, yyyy') :''
  }
},
methods:{
  submit(){
    console.log(this.title,this.content)
  }
},
}
</script>

<style>

</style>