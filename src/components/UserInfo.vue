<template>
  <aside class="user-info">
    <div class="header">
      <div class="img-wrapper">
        <img class="user-avatar" :src="this.user.avatar" alt="avatar" />
      </div>
      <div>
        <p>{{ this.user.username }}</p>
        <p>{{ this.user.email }}</p>
      </div>
    </div>
    <div class="info">
      <h3 class="info__header">Info</h3>
      <div class="info__content">
        <p>Name: {{ user.first_name }} {{ user.last_name }}</p>
        <p>Age: {{ getAge(user.date_of_birth) }}</p>
        <p>Employment: {{ user.employment.title }}</p>
        <p>Gender: {{ user.gender }}</p>
      </div>
    </div>
  </aside>
</template>

<script>
import { getAge } from "../utils/date";
export default {
  props: {
    user: Object,
  },
  methods: {
    getAge,
  },
};
</script>

<style lang="scss" scoped>
.user-info {
  background: #1f1d2b;
  padding: 20px;
  border-right: 1px solid gray;
  width: 300px;
  height: 100%;
  color: white;

  .header {
    display: flex;
    align-items: center;
    p {
      margin-top: 8px;
    }
    .img-wrapper {
      width: 60px;
      height: 60px;
      background: rgb(43, 172, 161);
      border-radius: 50%;
      margin-right: 10px;

      .user-avatar {
        text-align: center;
        line-height: 60px;
        border-radius: 50%;
        width: 60px;
        height: 60px;
      }
    }
  }
  .info__header {
    margin: 30px 0;
  }
  .info__content p {
    margin-top: 10px;
  }
}
@media screen and (max-width: 768px) {
  .user-info {
    width: 100%;
    height: auto;
  }
}
</style>
