<template>
  <div class="main">
    <div class="header">
      <div class="header_items">
        <img src="@/assets/logo.png" alt="chuk norris little logo" />
        <p>Chuck Norris</p>
      </div>
    </div>
    <div class="container">
      <p class="title">Categories</p>
      <div class="themes">
        <div v-for="item in data" :key="item.id">
          <div @click="getCitate(item.id)" class="themes-tag">
            <p class="themes-text">{{ item.theme }}</p>
          </div>
        </div>
      </div>
      <Quotes :quotes="quotes" />
    </div>
  </div>
</template>

<script>
import Quotes from "./components/Quotes.vue";

export default {
  components: { Quotes },
  data() {
    return {
      data: [
        {
          theme: "career",
          citate: "-“Hi, Im Chuck Norris and I start tomorrow. Any questions?”",
        },
        {
          theme: "love",
          citate:
            "-“What we have once enjoyed we can never lose. All that we love deeply becomes a part of us.”",
        },
        {
          theme: "celebrity",
          citate:
            "-“There is no such thing as fun for the whole family.” —Jerry Seinfeld",
        },
        {
          theme: "fashion",
          citate:
            " -“Clothes mean nothing until someone lives in them. Marc Jacobs”",
        },
        { theme: "money", citate: "-“Money often costs too much.”" },
        { theme: "music", citate: "-“Music is a moral law.”" },
        {
          theme: "political",
          citate:
            "-“Your time is limited, so don't waste it living someone else's life.”",
        },
        {
          theme: "sport",
          citate:
            "-“ The only way to prove that you're a good sport is to lose.””",
        },
        { theme: "travel", citate: "-“Travel is my therapy.”" },
      ],
      quotes: [],
    };
  },
  computed: {
    addKey() {
      this.data = this.data.map((item, id) => {
        let uniqId = parseInt(id);
        return Object.assign(item, { id: uniqId + 1 });
      });
    },
  },

  methods: {
    getCitate(item) {
      if ((this.quotes = [])) {
        return (this.quotes = this.data.filter(function (i, index) {
          return index + 1 === item;
        }));
      }
    },
  },
  mounted() {
    this.addKey;
  },
};
</script>

<style>
body {
  margin: 0 auto;
  background: #e5e5e5;
}
.container {
  height: 100vh;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}
.themes {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: space-between;
  align-content: center;
  margin-bottom: 150px;
}
.themes-tag {
  background: #ffffff;
  border: 0.75px solid #1c1c39;
  box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.24);
  border: none;
  border-radius: 20px;
  width: 80px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}
.themes-tag:hover {
  background: #422ed4;
}
.themes-text {
  font-family: "Raleway";
  font-style: normal;
  font-weight: 800;
  font-size: 16px;
  line-height: 19px;
  text-align: center;
  color: #1c1c39;
}
.themes-text:hover {
  color: #ffffff;
}
.title {
  font-family: "Raleway";
  font-style: normal;
  font-weight: 800;
  font-size: 50px;
  line-height: 59px;
  /* identical to box height */
  color: #1c1c39;
  text-align: center;
  margin-top: 50px;
}
.header {
  position: fixed;
  width: 100%;
  height: 35px;
  background: #422ed4;
  color: #ffffff;
}
.header_items {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 150px;
  align-items: center;
  margin-left: 20px;
}
.header_items img {
  width: 35px;
  height: 35px;
}
</style>
