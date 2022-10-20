<template>
  <div class="quote-container">
    <div v-if="this.quotes.length < 1" class="some-class">
      <p class="quote_text">Select some quote theme</p>
    </div>

    <div v-for="quote in quotes" :key="quote.id">
      <p class="quote_text">{{ quote.citate }}</p>
    </div>

    <div>
      <img src="@/assets/chuckNorris.png" alt="Chuk Norris" />
    </div>
  </div>
</template>

<script>
export default {
  name: "quotes",
  props: {
    quotes: {
      type: [Object, Array],
    },
  },
};
</script>

<style scoped>
.quote-container {
  height: 140px;
  width: 900px;
  background: #422ed4;
  box-shadow: 0px 100px 80px rgba(80, 76, 103, 0.07),
    0px 0px 10.0172px rgba(80, 76, 103, 0.035);
  border-radius: 25px;
  margin-bottom: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.quote_text {
  font-family: "Raleway";
  font-style: normal;
  font-weight: 600;
  font-size: 20px;
  line-height: 150%;
  /* or 30px */
  width: 800px;
  padding: 10px;
  display: flex;
  justify-content: center;

  color: #ffffff;
}
@media (max-width: 900px) {
  .quote-container {
    max-width: 600px;
  }
  .quote_text {
    max-width: 600px;
  }
}
@media (max-width: 600px) {
  .quote-container {
    max-width: 300px;
  }
  .quote_text {
    max-width: 300px;
  }
}
</style>
