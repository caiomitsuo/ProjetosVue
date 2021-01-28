<template>
  <div class="content">
    <h1 class="content-title">Informações sobre o Produto</h1>
    <table>
      <tr class="header">
        <th class="header-title">Cultura</th>
        <th class="header-title">Ano</th>
        <th class="header-title">A fixar</th>
        <th class="header-title">Entregue</th>
        <th class="header-title">Fixado</th>
      </tr>
      <tr v-for="(item, index) in items" :key="index">
        <td
          class="table-info"
          :class="`table-info--${item.culture.toLowerCase()}`"
        >
          {{ item.culture }}
        </td>
        <td class="table-info">{{ item.crop }}</td>
        <td class="table-info">{{ item.toFix | formatValor}}</td>
        <td class="table-info">{{ item.delivered | formatValor }}</td>
        <td class="table-info">{{ item.fixed | formatValor }}</td>
      </tr>
    </table>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data() {
    return {
      items: [],
    };
  },
  filters: {
    formatValor(item) {
      return Intl.NumberFormat({ maximumSignificantDigits: 3 }).format(
        item
      );
    },
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
<style lang="scss" src="../assets/styles/pages/info.scss" scoped></style>
