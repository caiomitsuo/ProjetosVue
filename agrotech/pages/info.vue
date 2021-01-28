<template>
  <table>
    <tr>
      <th>Cultura</th>
      <th>Ano</th>
      <th>A fixar</th>
      <th>Entregue</th>
      <th>Fixado</th>
    </tr>
    <tr v-for="(item, index) in items" :keu="index">
      <td>{{ item.culture }}</td>
      <td>{{ item.crop }}</td>
      <td>{{ item.toFix }}</td>
      <td>{{ item.delivered }}</td>
      <td>{{ item.fixed }}</td>
    </tr>
  </table>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      items: [],
    };
  },
  mounted() {
    this.getItem();
  },
  methods: {
    getItem() {
      axios
        .get("https://run.mocky.io/v3/d810a6b5-f52c-4807-a47e-363a7ca3ee57")
        .then((response) => {
          this.items = response.data;
        });
    },
  },
};
</script>
<style></style>
