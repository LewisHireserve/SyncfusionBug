<template>
  <div id="app">
    <ejs-kanban
      id="kanban"
      keyField="Status"
      :dataSource="kanbanData"
      :cardSettings="cardSettings"
    >
      <e-columns>
        <e-column headerText="To Do" keyField="Open"></e-column>
        <e-column headerText="In Progress" keyField="InProgress"></e-column>
        <e-column headerText="Testing" keyField="Testing"></e-column>
        <e-column headerText="Done" keyField="Close"></e-column>
      </e-columns>
      <template v-slot:cardsTemplate="{ data }">
        <KanbanCard> {{ data }} </KanbanCard>
      </template>
    </ejs-kanban>
  </div>
</template>

<script>
import Vue from "vue";
import KanbanCard from "./components/KanbanCard.vue";
import { data } from "./data.js";
import { KanbanPlugin } from "@syncfusion/ej2-vue-kanban";
Vue.use(KanbanPlugin);

export default {
  name: "App",
  components: {
    KanbanCard,
  },
  provide() {
    return {
      foo: "bar",
    };
  },
  data() {
    return {
      kanbanData: data,
      cardSettings: {
        headerField: "Id",
        template: "cardsTemplate",
      },
    };
  },
};
</script>

<style>
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-layouts/styles/material.css";
@import "../node_modules/@syncfusion/ej2-dropdowns/styles/material.css";
@import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../node_modules/@syncfusion/ej2-navigations/styles/material.css";
@import "../node_modules/@syncfusion/ej2-popups/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-kanban/styles/material.css";

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.e-filterbar {
  display: none;
}
</style>
