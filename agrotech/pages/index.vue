<template>
 <div>
   <ul>
     <li v-for="(user,u) in users" :key="u">
       {{user.culture}}
     </li>
   </ul>
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

<style></style>
