<template>
  <div class="col-xs-12 col-sm-6" v-if="server">
    <p>Server #{{ server.id}}: {{ server.status }}</p>
    <button @click="resetStatus">reset</button>
  </div>
</template>

<script>
import eventBus from "../eventBus";

export default {
  data() {
    return {
      server: null
    };
  },
  methods: {
    resetStatus() {
      if (this.server) {
        this.server.status = "Normal";
      }
    }
  },
  mounted() {
    eventBus.$on("server-selected", server => (this.server = server));
  }
};
</script>