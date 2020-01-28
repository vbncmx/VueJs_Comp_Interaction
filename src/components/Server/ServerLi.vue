<template>
  <li class="list-group-item">
    <button @click="click">
      Server #{{ server.id }}
    </button>    
  </li>
</template>

<script>
import eventBus from "../eventBus"

export default {
  props: {
    server: {
      required: true
    }
  },
  methods: {
    click() {
      eventBus.$emit("server-selected", this.server);
    }
  }
};
</script>