<template>
  <div class="" >
    <v-list flat>
      <v-list-item @click="doneTask(task.id)" :class="{'blue accent-1' : task.done}" v-for="task in tasks" :key="task.id">
        <template v-slot:default>
          <v-list-item-action>
            <v-checkbox :input-value="task.done" color="primary"></v-checkbox>
          </v-list-item-action>

          <v-list-item-content>
            <v-list-item-title :class="{'text-decoration-line-through' : task.done}"  >{{ task.title }}</v-list-item-title>
          </v-list-item-content>
        </template>
      </v-list-item>
    </v-list>
  </div>
</template>

<script>
// Components

export default {
  name: "HomeView",

  components: {},
  data() {
    return {
      settings: [],
      tasks: [
        { id: 1, done: false, title: "wakeup" },
        { id: 2, done: false, title: "eat" },
        { id: 3, done: false, title: "walk" },
      ],
    };
  },
  methods: {
    doneTask(id) {
      let task = this.tasks.filter((task) => task.id === id);
       task[0].done=!task[0].done
    },
  },
};
</script>
