<template>
  <ul>
    <li :key="log.id" v-for="log in logs">
      <span>identificador del servicio: {{ log.serviceId }}</span>
      <span>tipo: {{ log.type }}</span>
      <span>Ocurrido en: {{ log.occurredAt }}</span>
      <span>Data: </span>
      <json-view :data="log.data" />
    </li>
  </ul>
</template>

<script>
import { JSONView } from "vue-json-component";

export default {
  name: "LogsList",
  props: ["logs"],
  components: { "json-view": JSONView }
};
</script>

<style scoped></style>
