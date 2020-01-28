<template>
  <div class="col-xs-12 col-sm-6">
    <ul class="list-group">
      <server-li v-for="s in servers" :server="s" :key="s.id"></server-li>
    </ul>
  </div>
</template>

<script>
import ServerLi from "./ServerLi.vue";
export default {
  components: {
    "server-li": ServerLi
  },
  data() {
    return {
      servers: [
        { id: 1, status: "Normal" },
        { id: 2, status: "Critical" },
        { id: 3, status: "Unknown" },
        { id: 4, status: "Normal" }
      ]
    };
  }
};
</script>

<style>
</style>
