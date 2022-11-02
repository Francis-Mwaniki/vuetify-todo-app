<template>
  <div class="">
    <v-text-field
      outlined
      label="Add todo.."
      append-icon="mdi-plus"
      hide-details
      @click:append="addTask"
      @keyup.enter="addTask"
      clearable
      class="pa-3"
      v-model="newText"
    ></v-text-field>
    <v-list flat>
      <v-list-item
        @click="doneTask(task.id)"
        :class="{ 'blue accent-1': task.done }"
        v-for="task in tasks"
        :key="task.id"
      >
        <template v-slot:default>
          <v-list-item-action>
            <v-checkbox :input-value="task.done" color="primary"></v-checkbox>
          </v-list-item-action>

          <v-list-item-content>
            <v-list-item-title
              :class="{ 'text-decoration-line-through': task.done }"
              >{{ task.title }}</v-list-item-title
            >
          </v-list-item-content>
          <v-list-item-action>
            <v-icon color="primary" @click.stop="deleteTask(task.id)"
              >mdi-delete-circle</v-icon
            >
          </v-list-item-action>
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
      newText: "",
      settings: [],
      tasks: [
        { id: 1, done: false, title: "wakeup" },
        { id: 2, done: false, title: "eat" },
        { id: 3, done: false, title: "walk" },
      ],
    };
  },
  methods: {
    addTask() {
      let newTask = {
        id: Date.now(),
        title: this.newText,
        done: false,
      };
      this.tasks.push(newTask);
    },
    doneTask(id) {
      let task = this.tasks.filter((task) => task.id === id);
      task[0].done = !task[0].done;
    },
    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id);
      this.newText = "";
    },
  },
};
</script>
