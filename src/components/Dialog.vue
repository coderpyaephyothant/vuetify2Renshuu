<template>
  <v-dialog
  width="700"
  v-model="successClose"
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
            <v-form
            ref="form"
            >

              <v-text-field
                v-model="title"
                label="Title"
                prepend-icon="mdi mdi-pen"
                :rules="inputRules"
              ></v-text-field>

                <v-textarea
                label="Content"
                prepend-icon="mdi mdi-text"
                v-model="content"
                :rules="inputRules"      
                ></v-textarea>

                <!-- Date Picker -->
                <v-row>
                  <v-col
                  cols="12"
                  md="4"
                  sm="12"
                  >
                  <v-menu>
                    <template v-slot:activator="{ on, attrs }">

                      <v-text-field
                        clearable
                        prepend-icon="mdi mdi-calendar-month"
                        label="Due Date"
                        readonly
                        v-model="formattedDate"
                        v-bind="attrs"
                        v-on="on"
                      :rules="inputRules"
                      ></v-text-field>

                    </template>

                    <v-date-picker
                      v-model="date"
                    ></v-date-picker>

                  </v-menu>
              </v-col>
            </v-row>
                <!-- Button -->
                <v-btn class="success mt-2 mx-0" depressed small @click="submit()" :loading="btnLoading">Submit</v-btn>
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
    date:null,
    inputRules:[
      v=> v.length >= 3 || 'Minimum length is 3 characters'
    ],
    btnLoading:false,
    successClose:false,
    successText:'Successfully Created!'
  }
},
computed:{
  formattedDate (){
    return this.date? format(this.date, 'MMMM dd, yyyy') :''
  }
},
methods:{
  submit(){
    if(this.$refs.form.validate()){
      // console.log(this.title,this.content)
        this.btnLoading = true
      setTimeout(() => {
        this.btnLoading = false
        this.successClose = false
        this.$emit('successfullyCreated', this.successText)
      }, 5000);
    }
  }
},
}
</script>

<style>

</style>