<template>
  <div class="container has-text-centered">
    <h2 class="title">My Profile</h2>
    <img :src="user.avatar_url" class="avatar" />
    <p>Name : {{ user.name }}</p>
    <p>Location : {{ user.location }}</p>
    <div class="columns is-multiline my-4">
      <div v-for="repo in repos" :key="repo.id" class="column is-3">
        <div class="card">
          <div class="card-content">
            <a
              :href="repo.html_url"
              target="_blank"
              rel="noopener noreferrer "
              >{{ repo.name }}</a
            >
            <p>Star : {{ repo.stargazers_count }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  async asyncData({ $axios }) {
    const [user, repos] = await Promise.all([
      $axios.$get('https://api.github.com/users/TinnakornChoompee'),
      $axios.$get(
        'https://api.github.com/users/TinnakornChoompee/repos?sort=pushed&per_page=100'
      ),
    ])
    return { user, repos }
  },
}
</script>
<style scoped>
.avatar {
  width: 128px;
  height: 128px;
}
</style>
