<template>
  <div>
    <table>
      <tbody>
        <tr v-for="dado in dados" :key="dado.id">
          <td>{{dado.id}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
        dados: Array,
    };
  },
  mounted() {
    this.getDados();
  },
  methods: {
    async getDados() {
        const response = await axios.get("https://run.mocky.io/v3/2a793688-2254-4663-8d2a-0b1845f16777")
        .then(response => {
          this.dados = response.data;
        })
        .catch((e) => console.log(e));
    },
  },
};
</script>

<style></style>
