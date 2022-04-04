<template>
  <div>
    <div v-if="beer" class="beer-card">
      <h2>Recommended beer</h2>
      <h3 class="beer-card__brand">
        Beer brand: <span>{{ beer.brand }}</span>
      </h3>
      <h3 class="beer-card__name">
        Beer name: <span>{{ beer.name }}</span>
      </h3>
    </div>
    <div v-else class="beer-card">
      <p>Looking for suitable beer for you...</p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      beer: null,
    };
  },
  mounted() {
    fetch("https://random-data-api.com/api/beer/random_beer")
      .then((res) => res.json())
      .then((data) => (this.beer = data))
      .catch((err) => console.log(err.message));
  },
};
</script>
