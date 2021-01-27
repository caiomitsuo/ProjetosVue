<template>
  <div class="card">
    <div class="card-logo">
      <h1 class="card-logo__title">Agrotech</h1>
    </div>
    <div class="card-content">
      <ul class="card-column">
        <strong class="card-content__title">Cultura</strong>
        <li
          v-for="(user, culture) in users"
          :key="culture"
          class="card-content__culture"
        >
          <p class="card-content__soja">{{ user.culture }}</p>
        </li>
      </ul>

      <ul class="card-column">
        <strong class="card-content__title">Umidade</strong>
        <li
          v-for="(user, impurity) in users"
          :key="impurity"
          class="card-content__culture"
        >
          <p class="card-content__humidity">{{ user.humidity }}</p>
        </li>
      </ul> 

      <ul class="card-column">
        <strong class="card-content__title">Colheita</strong>
        <li
          v-for="(user, cropYear) in users"
          :key="cropYear"
          class="card-content__culture"
        >
          <p class="card-content__colheita">{{ user.cropYear }}</p>
        </li>
      </ul>

      <ul class="card-column">
        <strong class="card-content__title">Impureza</strong>
        <li
          v-for="(user, branch) in users"
          :key="branch"
          class="card-content__culture"
        >
          <p class="card-content__impurity">{{ user.impurity }}</p>
        </li>
      </ul>

      <ul class="card-column">
        <strong class="card-content__title">Pedido</strong>
        <li
          v-for="(user, delivery) in users"
          :key="delivery"
          class="card-content__culture"
        >
          <p class="card-content__delivery">{{ user.deliveryId }}</p>
        </li>
      </ul>

      <ul class="card-column">
        <strong class="card-content__title">Motorista</strong>
        <li
          v-for="(user, branch) in users"
          :key="branch"
          class="card-content__culture"
        >
          <p class="card-content__driver">{{user.driver}}</p>
        </li>
      </ul>

      <ul class="card-column">
        <strong class="card-content__title">Filial</strong>
        <li
          v-for="(user, filial) in users"
          :key="filial"
          class="card-content__culture"
        >
          <p class="card-content__driver">{{user.branch}}</p>
        </li>
      </ul>
    </div>
  </div>
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
