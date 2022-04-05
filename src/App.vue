<template>
  <div class="bg-img"></div>
  <main>
    <header>
      <h1>Beer app</h1>
    </header>
    <div class="container">
      <UserCard />
      <BeerCard />
    </div>
  </main>
</template>

<script>
import UserCard from "./components/UserCard.vue";
import BeerCard from "./components/BeerCard.vue";

export default {
  name: 'App',
  components: {
    UserCard,
    BeerCard
  }
}
</script>
