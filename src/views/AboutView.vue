<template>
  <div class="about">
    <h1>This is an about page</h1>
    {{ user }}
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

<script>
import axios from "axios";
import { ref } from "vue";
export default {
  setup(props) {
    console.log(import.meta.env.VITE_TEXT);
    let user = ref();
    axios.get(import.meta.env.VITE_PATH).then((res) => {
      user.value = res.data;
    });
    return {
      user,
    };
  },
};
</script>
