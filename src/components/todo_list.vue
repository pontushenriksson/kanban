<template>
  <div class="controls">
    <div @click="add_task" class="add_btn">
      <i class="fas fa-tasks"></i>
      <div id="add_task" v-on:submit.prevent="addNewTodo">Add task</div>
    </div>
    <div @click="delete_prompt" class="delete_btn">
      <i class="fas fa-trash-alt"></i>
      <div id="delete_task">Delete task</div>
    </div>
    <div class="move_btn">
      <i class="fas fa-arrows-alt"></i>
      <div id="move_task">Move task</div>
    </div>
  </div>
  <div class="delete_">
    <div class="delete_prompt">
      <p class="prompt">Are you sure that you want to delete the task?</p>
      <br />
      <div class="prompt_options">
        <div class="delete_prompt_no"><i class="fas fa-save"></i>No</div>
        <div class="delete_prompt_yes"><i class="fas fa-trash-alt"></i>Yes</div>
      </div>
    </div>
  </div>

  <div class="boards">
    <div class="todo">
      <div class="todo_header">
        <p class="title">Todo</p>
      </div>
    </div>
    <div class="ip">
      <div class="todo_header">
        <p class="title">In progress</p>
      </div>
    </div>
    <div class="done">
      <div class="todo_header">
        <p class="title">Done</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "todo_list",
  props: {
    msg: String,
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  background: rgb(48, 49, 49);
}

.controls {
  display: flex;
  justify-content: space-evenly;
  width: 30vw;
  padding: 0 0 2vw 0;
}

.add_btn {
  width: 9vw;
  height: 3vw;
  background: #4dbb43;
  display: flex;
  align-items: center;
  justify-content: space-around;
  border-radius: 5%;
  color: #fff;
}

.delete_btn {
  width: 9vw;
  height: 3vw;
  background: #bb4343;
  display: flex;
  align-items: center;
  justify-content: space-around;
  border-radius: 5%;
  color: #fff;
}

.move_btn {
  width: 9vw;
  height: 3vw;
  background: #222222;
  display: flex;
  align-items: center;
  justify-content: space-around;
  border-radius: 5%;
  color: #fff;
}

.boards {
  display: flex;
  justify-content: space-evenly;
  width: 100%;
}

.title {
  color: #fff;
}

.todo_header,
.ip_header,
.done_header {
  display: flex;
  justify-content: left;
  padding: 0 0 0 2vw;
}

.todo,
.ip,
.done {
  width: 20vw;
  height: 40vh;
  background: #222222;
  border-radius: 5%;
}

/*Delete prompt*/
.delete_ {
  display: flex;
  justify-content: center;
  visibility: hidden;
  display: none;
}

.delete_prompt {
  z-index: 2;
  background: #fff;
  width: 30vw;
  height: 10vw;
  border-radius: 5%;
}
.prompt {
  padding-top: 1vw;
}
.prompt_options {
  justify-content: space-evenly;
  display: flex;
}

.delete_prompt_no {
  background: #4dbb43;
  width: 8vw;
  height: 2.5vw;
  display: flex;
  align-items: center;
  justify-content: space-around;
  border-radius: 5%;
}
.delete_prompt_yes {
  background: #bb4343;
  width: 8vw;
  height: 2.5vw;
  display: flex;
  align-items: center;
  justify-content: space-around;
  border-radius: 5%;
}
</style>
