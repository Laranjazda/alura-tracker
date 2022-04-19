<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para criação de nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
          v-model="description"
        />
      </div>

      <TimerTask @timerEnded="taskEnded"/>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TimerTask from "./TimerTask.vue";

export default defineComponent({
  name: "FormTask",
  components: {
    TimerTask,
  },
  data(){
      return{
          description: ""
      }
  },
  methods:{
      taskEnded(secondsTransform: number) : void{
          console.log("tempo da tarefa: " + secondsTransform)
          console.log("Descrição: " + this.description)
          this.description = ""
      }

  }
});
</script>