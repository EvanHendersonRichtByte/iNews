<template>
  <header>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <a class="navbar-brand" href="#"><span class="text-danger">i</span>News</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link" target="_blank" href="https://tribunnews.com/"
              >Tribun News</a
            >
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              target="_blank"
              href="https://www.antaranews.com/"
              >Antara News</a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link" target="_blank" href="https://www.kompas.com/"
              >Kompas</a
            >
          </li>
          <li class="nav-item">
            <a class="nav-link" target="_blank" href="https://www.detik.com/"
              >Detik News</a
            >
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>
