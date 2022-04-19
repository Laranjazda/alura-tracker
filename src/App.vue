<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar />
    </div>

    <div class="column is-three-quarter">
      <FormTask />
    </div>
    <section class="section is-medium">
      <UserLogin />
    </section>
</main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import SideBar from './components/SideBar.vue';
import FormTask from './components/FormTask.vue';
import UserLogin from './components/UserLogin.vue';

export default defineComponent({
  name: 'App',
  components:{
    SideBar,
    FormTask,
    UserLogin
  }
});
</script>

<style scoped>
section{
  padding: auto;
}

</style>
