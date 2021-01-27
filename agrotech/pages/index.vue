<template>
  <table>
    <tr class="table-title">
      <th class="table-title">Cultura</th>
      <th class="table-title">Impureza</th>
      <th class="table-title">Colheita</th>
      <th class="table-title">Local</th>
      <th class="table-title">Pedido</th>
    </tr>
    <tr v-for="(user, c) in users" :key="c">
      <td
        class="table-content"
        :class="`table-content--${user.culture.toLowerCase()}`"
      >
        {{ user.culture }}
      </td>
      <td class="table-content">
        {{ user.impurity }}
      </td>
      <td class="table-content">
        {{ user.humidity }}
      </td>
      <td class="table-content">
        {{ user.branch }}
      </td>
      <td class="table-content">
        {{ user.deliveryId }}
      </td>
    </tr>
  </table>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      users: [],
    };
  },
  mounted() {
    this.getUsers();
  },
  methods: {
    getUsers() {
      axios
        .get("https://run.mocky.io/v3/22a9cdc9-ee02-4a10-b27f-568465c3b85b")
        .then((response) => {
          this.users = response.data.content;
        });
    },
  },
};
</script>
<style lang="scss" src="../assets/styles/pages/index.scss" scoped></style>
