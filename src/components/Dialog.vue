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
            This is Dialog
        </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {

}
</script>

<style>

</style>