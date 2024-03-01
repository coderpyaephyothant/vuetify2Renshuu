<template>
<div>
  <h3 class="grey--text">Dashboard</h3>
  <v-container fluid>
    <div v-if="projects.length > 0">
      <v-row class="my-2">
        <v-col>
    <v-tooltip bottom>
      <template v-slot:activator="{ on, attrs }">
          <v-btn 
          class="mx-2"
          depressed
          @click="sortBy('title')"
          v-bind="attrs"
          v-on="on"
          >
            <v-icon 
            class="mdi mdi-calendar-text" 
            small
            color="green darken-2"
            ></v-icon>
            <span class="text-lowercase">By Title</span>
          </v-btn>
          </template>
      <span>SortByTitle</span>
    </v-tooltip>
<v-tooltip bottom>
      <template v-slot:activator="{ on, attrs }">
          <v-btn 
          class="mx-2"
          depressed
          @click="sortBy('developer')"
          v-bind="attrs"
          v-on="on">
            <v-icon 
            class="mdi mdi-account" 
            small
            color="blue darken-2"
            ></v-icon>
            <span class="text-lowercase">By Developer</span>
          </v-btn>
          </template>
      <span>SortByDeveloper</span>
          </v-tooltip>
        </v-col>
      </v-row>
     <v-card
          v-for="project in projects" :key="project.id"
          :class="`pa-2 project ${project.status}`"
          tile
        >
          <v-row 
          >
            <v-col  class="" md="6" sm="12">
              <h4 class="grey--text">プロジェクト名</h4>
              <div>{{project.title}}</div>
            </v-col>
            <v-col  class="" md="2" sm="4">
              <h4 class="grey--text">開発者</h4>
              <div>{{project.developer}}</div>
            </v-col>
            <v-col  class="" md="2" sm="4">
              <h4 class="grey--text">発売日</h4>
              <div>{{project.due_date}}</div>
            </v-col>
            <v-col  class="" md="2" sm="4">
              <!-- <h4 class="grey--text">ステータス</h4> -->
              <div class="float-end">
                <v-chip
                :class="`${project.status} white--text`">
                  {{project.status}}
                </v-chip>
              </div>
            </v-col>
            <v-divider></v-divider>
          </v-row> 
        </v-card>
    </div>
      
  </v-container>
</div> 
</template>

<script>

  export default {
    name: 'Home',

    components: {
    },
    data(){
      return {
         projects : [
  {
    id:1,
    title: 'タスク1',
    developer: '山田 太郎',
    due_date: '2024-03-10',
    status: 'ongoing',
  },
  {
    id:2,
    title: 'タスク2',
    developer: '佐藤 花子',
    due_date: '2024-03-15',
    status: 'complete',
  },
  {
    id:3,
    title: 'タスク3',
    developer: '鈴木 健太',
    due_date: '2024-03-20',
    status: 'complete',
  },
  {
    id:4,
    title: 'タスク4',
    developer: '田中 一郎',
    due_date: '2024-03-25',
    status: 'overdue',
  },
]
      }
    },
    methods:{
      sortBy(prop){
        // alert(prop)
        this.projects.sort((a,b)=>a[prop] < b[prop] ? -1 : 1)
      }
    }
  }
</script>

<style scoped>
.project.ongoing {
  border-left: 4px solid #00ff91a7;
}
.project.complete {
  border-left: 4px solid #ff00e1a7;
}
.project.overdue {
  border-left: 4px solid #5500ffa7;
}
.v-chip.ongoing{
background: #00ff91a7;
}
.v-chip.complete{
background: #ff00e1a7;
}
.v-chip.overdue{
background: #5500ffa7;
}
</style>
