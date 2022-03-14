<script>
export default {
  name: "App",
  data() {
    return {
      news: [],
      highlight: [],
      isLoading: true,
    };
  },
  methods: {
    getImage(index) {
      return this.news.data[index].image;
    },
  },
  async mounted() {
    await axios
      .get(
        "https://berita-api-d8qkqgisu-satyawikananda.vercel.app/v1/tribun-news"
      )
      .then(({ data }) => {
        this.highlight = data.data.filter((_, i) => i >= 0 && i <= 2);
        this.news = data.data.filter((_, i) => i > 2);
      })
      .catch((err) => {
        throw err;
      });
    this.isLoading = false;
  },
  components: { Carousel, Header },
};

import axios from "axios";
import Carousel from "./components/Carousel.vue";
import Header from "./components/Header.vue";
</script>

<template>
  <main v-if="!isLoading">
    <Header />
    <div class="container">
      <Carousel :news="news" :highlight="highlight" />
      <div class="col-md-12">
        <div class="row justify-content-center justify-content-sm-center justify-content-md-between">
          <div
            class="card mt-5"
            style="width: 21rem"
            :key="n.title"
            v-for="n in news"
          >
            <img class="card-img-top" :src="n.image" alt="Card image cap" />
            <div class="card-body">
              <h5 class="card-title">{{ n.title }}</h5>
              <p class="card-text">
                {{ n.contentSnippet }}
              </p>
              <a :href="n.link" class="btn btn-dark">Continue Reading</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>