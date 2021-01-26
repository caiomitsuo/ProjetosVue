<template>
  <div class="card">
    <div class="card-content">
      <ul class="card-column">
        <strong class="card-content-title">Cultura</strong>
        <li
          v-for="(user, culture) in users"
          :key="culture"
          class="card-content__culture"
        >
          <p class="card-content__soja">{{ user.culture }}</p>
        </li>
      </ul>

      <ul class="card-column">
        <strong class="card-content-title">Impureza</strong>
        <li
          v-for="(user, impurity) in users"
          :key="impurity"
          class="card-content__culture"
        >
          <p class="card-culture__impurity">{{ user.impurity }}</p>
        </li>
      </ul>

      <ul class="card-column">
        <strong class="card-content-title">Colheita</strong>
        <li
          v-for="(user, cropYear) in users"
          :key="cropYear"
          class="card-content__culture"
        >
          <p class="card-culture__colheita">{{ user.cropYear }}</p>
        </li>
      </ul>

      <ul class="card-column">
        <strong class="card-content-title">Local</strong>
        <li
          v-for="(user, branch) in users"
          :key="branch"
          class="card-content__culture"
        >
          <p class="card-branch__local">{{ user.branch }}</p>
        </li>
      </ul>

      <ul class="card-column">
        <strong class="card-content-title">Pedido</strong>
        <li
          v-for="(user, delivery) in users"
          :key="delivery"
          class="card-content__culture"
        >
          <p class="card-culture__title">{{ user.deliveryId }}</p>
        </li>
      </ul>

      <ul class="card-column">
        <strong class="card-content-title">Status</strong>
        <li
          v-for="(user, status) in users"
          :key="status"
          class="card-content__culture"
        >
          <p class="card-content__btn">Entregue</p>
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
        .get("https://run.mocky.io/v3/2a793688-2254-4663-8d2a-0b1845f16777")
        .then((response) => {
          this.users = response.data.content;
        });
    },
  },
};
</script>
<style lang="scss" src="../assets/styles/pages/index.scss" scoped></style>
