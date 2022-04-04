<template>
  <div>
    <div v-if="user" class="user-card">
      <img :src="user.avatar" :alt="user.name" class="user-card__img" />
      <h2 class="user-card__name">
        {{ user.first_name }} {{ user.last_name }}
      </h2>
      <h3 class="user-card__age">
        Age:
        <span>{{
          new Date().getFullYear() - user.date_of_birth.slice(0, 4)
        }}</span>
      </h3>
      <h3 class="use-card__work-place">
        City: <span>{{ user.address.city }}</span>
      </h3>
      <h3 class="use-card__work-place">
        Title: <span> {{ user.employment.title }}</span>
      </h3>
    </div>
    <div v-else class="user-card">
      <p>Loading user details...</p>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      user: null,
    };
  },
  mounted() {
    fetch("https://random-data-api.com/api/users/random_user")
      .then((res) => res.json())
      .then((data) => (this.user = data))
      .catch((err) => console.log(err.message));
  },
};
</script>
