<template>
  <div class="about">
    <h3 class="grey--text">Projects</h3>
    <v-container >
      <v-expansion-panels accordion>
      <v-expansion-panel
        v-for="pj in myProjects"
        :key="pj.id"
      >
        <v-expansion-panel-header>{{pj.title}}</v-expansion-panel-header>
        <v-expansion-panel-content class="grey--text">
          <!-- 6:28 / 10:22 -->
          <div class="font-weight-bold">due by {{pj.due_date}}</div>
          <div>{{pj.content}}</div>
        </v-expansion-panel-content>
      </v-expansion-panel>
    </v-expansion-panels>
  </v-container>
  </div>
</template>
<script>
export default {
    data(){
      return {
        projects : [
  {
    id:1,
    title: ' Introduction to HTML5',
    developer: 'Pyae Phyo Thant',
    due_date: '2024-03-10',
    status: 'ongoing',
    content : 'Explore the foundational markup language, HTML5, and its latest features. Learn how to structure your web documents for enhanced semantics and accessibility. Dive into the world of elements, attributes, and the power of HTML5 in modern web development.'
  },
  {
    id:2,
    title: 'CSS Grid Layout Essentials',
    developer: 'Pyae Phyo Thant',
    due_date: '2024-03-15',
    status: 'complete',
    content : 'Master the art of layout design with CSS Grid. Unleash the potential of responsive and dynamic page structures. Discover how to create complex grids, control placement, and achieve stunning visual layouts. Elevate your CSS skills and bring a new level of sophistication to your web projects.'
  },
  {
    id:3,
    title: 'JavaScript Fundamentals for Beginners',
    developer: 'Ko Phoe Ngal',
    due_date: '2024-03-20',
    status: 'complete',
    content : 'Begin your journey into the world of programming with JavaScript. From variables and data types to control flow and functions, grasp the core concepts that make JavaScript the language of the web. Start building interactive and dynamic websites, and lay the foundation for more advanced scripting.'
  },
  {
    id:4,
    title: 'Optimizing Website Performance with SEO',
    developer: 'Paing Zay',
    due_date: '2024-03-25',
    status: 'overdue',
    content : "Enhance your website's visibility on search engines through Search Engine Optimization (SEO) techniques. Learn how to optimize content, meta tags, and images for better rankings. Understand the importance of site speed and mobile-friendliness. Unlock the secrets to attracting more organic traffic and maximizing your online presence."
  },
]
      }
    },
    computed:{
      myProjects(){
      return    this.projects.filter(prj => 
           prj.developer == 'Pyae Phyo Thant'
        )
      }
    }
}
</script>

