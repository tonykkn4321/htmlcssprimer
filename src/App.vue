<template>
  <div>
    <h4 class="bg-primary text-white text-center p-2">
      Adam's To Do List
    </h4>
      <div class="container-fluid p-4">
        <div class="row">
          <div class="col font-weight-bold">Task</div>
          <div class="col-2 font-weight-bold">Done</div>
        </div>
        <div class="row" v-for="t in tasks" v-bind:key="t.action">
          <div class="col">{{t.action}}</div>
          <div class="col-2">{{t.done}}</div>
        </div>
      </div>
  </div>
  <div class="form-group m-2">
    <label>New Item:</label>
    <input v-model="newItemText" class="form-control" />
  </div>
    <div class="text-center">
    <button class="btn btn-primary" v-on:click="addNewTodo">
      Add
    </button>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      tasks: [{ action: "Buy Flowers", done: false },
              { action: "Get Shoes", done: false },
              { action: "Collect Tickets", done: true },
              { action: "Call Joe", done: false }],
              newItemText: ""
    }
  },
  methods: {
    addNewTodo() {
      this.tasks.push({
        action: this.newItemText,
        done: false
      });
        this.newItemText = "";
      }
    }
}
</script>
