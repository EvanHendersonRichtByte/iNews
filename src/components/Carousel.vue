<template>
  <div id="mainCarousel" class="carousel slide" data-ride="carousel">
    <ol class="carousel-indicators">
      <li data-target="#mainCarousel" data-slide-to="0" class="active"></li>
      <li data-target="#mainCarousel" data-slide-to="1"></li>
      <li data-target="#mainCarousel" data-slide-to="2"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img
          class="d-block w-100"
          :src="highlight[0].image"
          alt="First slide"
        />
        <div class="c-overlay"></div>
        <div class="carousel-caption d-none d-md-block">
          <h5>{{ highlight[0].title }}</h5>
          <p>{{ highlight[0].contentSnippet }}</p>
        </div>
      </div>
      <div class="carousel-item">
        <img
          class="d-block w-100"
          :src="highlight[1].image"
          alt="Second slide"
        />
        <div class="c-overlay"></div>
        <div class="carousel-caption d-none d-md-block">
          <h5>{{ highlight[1].title }}</h5>
          <p>{{ highlight[1].contentSnippet }}</p>
        </div>
      </div>
      <div class="carousel-item">
        <img
          class="d-block w-100"
          :src="highlight[2].image"
          alt="Third slide"
        />
        <div class="c-overlay"></div>
        <div class="carousel-caption d-none d-md-block">
          <h5>{{ highlight[2].title }}</h5>
          <p>{{ highlight[2].contentSnippet }}</p>
        </div>
      </div>
    </div>
    <a
      class="carousel-control-prev"
      href="#mainCarousel"
      role="button"
      data-slide="prev"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a
      class="carousel-control-next"
      href="#mainCarousel"
      role="button"
      data-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
  </div>
</template>

<script>
export default {
  name: "Carousel",
  props: {
    news: Array,
    highlight: Array,
  },
};
</script>
