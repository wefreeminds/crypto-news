<template>
  <b-container>
    <b-jumbotron bg-variant="dark" text-variant="white">
      <template slot="header">
        <span class="d-none d-md-block">Crypto conversion</span>
      </template>

      <template slot="lead">
        This tool allows you to quickly compare two cryptocurrencies. We use
        latest pricing data from <b-link class="text-secondary" href="https://min-api.cryptocompare.com/">CryptoCurrency API</b-link>.
      </template>

      <Converter class="converter mt-5" />
    </b-jumbotron>

    <Trends class="mb-5 px-4" />
  </b-container>
</template>

<script>
import Converter from "../components/Converter/Converter.vue";
import Trends from "../components/Trends/Trends.vue";

export default {
  name: "HomeScreen",

  components: {
    Converter,
    Trends
  }
};
</script>

<style lang="scss" scoped>
.jumbotron {
  position: relative;

  &::before {
    position: absolute;
    left: 15px;
    top: 0px;

    background-image: url("/images/map.png");
    background-repeat: no-repeat;
    background-size: contain;
    background-position: center left;

    width: 450px;
    height: 300px;

    content: "";

    @media screen and (max-width: 480px) {
      left: 0;

      width: 100%;
      height: 200px;
    }
  }

  .display-3,
  .lead {
    max-width: 600px;

    @media screen and (max-width: 820px) {
      margin: 0 auto;

      text-align: center;
    }
  }
}

@media screen and (max-width: 820px) {
  .converter {
    margin: 0 auto;
  }
}
</style>
