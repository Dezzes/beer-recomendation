<template>
  <div class="content">
    <h1 class="content__title">Your recomended beer</h1>
    <div class="content__info">
      <div class="content__beer-info">
        <p><strong>Brand: </strong>{{ beer.brand }}</p>
        <p><strong>Name: </strong>{{ beer.name }}</p>
        <p><strong>Style: </strong>{{ beer.style }}</p>
        <p><strong>Alcohol: </strong>{{ beer.alcohol }}</p>
      </div>
      <div class="content__img-container">
        <img src="../assets/img/beer-icon.png" alt="beer-icon" />
      </div>
    </div>
    <button @click="changeBeer" class="content__btn">Change it</button>
  </div>
</template>

<script>
export default {
  props: {
    beer: Object,
  },
  methods: {
    changeBeer() {
      this.$emit("fetchBeer");
    },
  },
};
</script>

<style lang="scss" scoped>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  flex: 1;
  padding: 20px;
  .content__title {
    display: flex;
    justify-content: center;
    margin-top: 20px;
  }
  .content__info {
    display: flex;
    justify-content: center;
    margin-top: 50px;
    .content__beer-info {
      width: 300px;
    }
    p {
      font-size: 20px;
      line-height: 30px;
    }
  }
  .content__img-container {
    display: flex;
    justify-content: center;
    align-items: center;
    img {
      width: 100px;
      height: 100px;
    }
  }
  .content__btn {
    display: flex;
    justify-content: center;
    width: 150px;
    border-color: #e0b668;
    background: #e0b668;
    padding: 10px;
    margin-top: 20px;
    border-radius: 10px;
  }
}
@media screen and (max-width: 768px) {
  .content {
    justify-content: flex-start;
    .content__info {
      .content__beer-info {
        width: auto;
      }
    }
  }
}
</style>
