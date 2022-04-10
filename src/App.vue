<template>
  <div class="content">
    <user-info :user="user" />
    <beer-item :beer="beer" @fetchBeer="fetchBeer" />
  </div>
</template>

<script>
import axios from "axios";

import UserInfo from "./components/UserInfo.vue";
import BeerItem from "./components/BeerItem.vue";

export default {
  components: { UserInfo, BeerItem },
  data() {
    return {
      beer: {
        brand: "",
        name: "",
        style: "",
        alcohol: "",
      },
      user: {
        avatar: "",
        employment: {
          title: "",
        },
        date_of_birth: "",
        gender: "",
      },
    };
  },
  methods: {
    async fetchBeer() {
      const response = await axios.get(
        "https://random-data-api.com/api/beer/random_beer"
      );
      this.beer = response.data;
    },
    async fetchUser() {
      await axios
        .get("https://random-data-api.com/api/users/random_user ")
        .then((response) => {
          this.user = response.data;
          console.log(this.user);
        });
    },
  },
  mounted() {
    this.fetchBeer();
    this.fetchUser();
  },
};
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  width: 100%;
  background-color: rgba(#e0b668, 0.5);
}

@media screen and (max-width: 768px) {
  .content {
    flex-direction: column;
  }
}
</style>
>
