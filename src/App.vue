<script>
export default {
  name: "App",
  data() {
    return {
      news: [],
      highlight: {},
      input: "example",
      test: "",
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
        this.highlight = data.data[0];
        this.news = data.data.filter((v, i) => i !== 0);
        console.log(this.news);
      })
      .catch((err) => {
        throw err;
      });
  },
};

import axios from "axios";
</script>

<template>
  <main class="container">
    <div class="p-4 p-md-5 mb-4 text-white rounded bg-dark">
      <div class="col-md-6 px-0">
        <h1 class="display-4 fst-italic">
          {{ highlight.title }}
        </h1>
        <p class="lead my-3">
          {{ highlight.contentSnippet }}
        </p>
        <p class="lead mb-0">
          <a :href="highlight.link" target="_blank" class="text-white fw-bold"
            >Continue reading...</a
          >
        </p>
      </div>
    </div>

    <div class="row mb-2">
      <div class="col-md-6" :key="data.title" v-for="data in news">
        <div
          class="
            row
            g-0
            border
            rounded
            overflow-hidden
            flex-md-row
            mb-4
            shadow-sm
            h-md-250
            position-relative
          "
        >
          <div class="col p-4 d-flex flex-column position-static">
            <strong class="d-inline-block mb-2 text-success">Latest</strong>
            <h3 class="mb-0">{{ data.title }}</h3>
            <div class="mb-1 text-muted">
              {{ new Date(data.isoDate).toUTCString() }}
            </div>
            <p class="mb-auto">
              {{ data.contentSnippet }}
            </p>
            <a :href="data.link" target="_blank" class="stretched-link"
              >Continue reading</a
            >
          </div>
          <div class="col-auto d-none d-lg-block">
            <img :src="data.image" width="200" alt="Gambar Tidak Ditemukan" />
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style>
@import "bootstrap/dist/css/bootstrap.css";
</style>
