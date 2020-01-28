<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="server">Server #{{ server.id}}: {{ server.status }}</p>
    </div>

</template>

<script>
import eventBus from "../eventBus"

export default {
  data() {
    return {
      server: null
    }
  },
  mounted() {
    eventBus.$on("server-selected", server => this.server = server)
  }
}
</script>