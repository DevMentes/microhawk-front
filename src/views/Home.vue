<template>
  <div class="home">
    <logs-list :logs="logs" />
  </div>
</template>

<script>
import LogsList from "../components/LogsList";
import axios from "axios";

export default {
  name: "home",
  components: { LogsList },
  data: () => {
    return {
      logs: []
    };
  },
  async mounted() {
    try {
      const response = await axios.get("http://localhost:4000/logger/logs");
      this.logs = response.data.data;
    } catch (error) {
      alert("Estamos teniendo problemas, intentalo mas tarde.");
    }
  }
};
</script>
