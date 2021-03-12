<template>
  <div class="home">
    <h1>Home page</h1>
    <div class="user-list">
      <router-link 
        v-for="user in users" 
        :to="{name: 'UserProfile', params: { userId: user.id }}"
        :key="user.id"
      >
        <h3 class="user-list__user-title">
          {{ user.username }}
        </h3>
      </router-link>
    </div>
  </div>
</template>

<script>
import { users } from '../assets/users'

export default {
  name: 'Home',
  setup() {
    return {
      users
    }
  }
}
</script>


<style lang="scss" scoped>
.home {
  padding: 50px 5%;

  .user-list {
    display: flex;
    flex-direction: column;
    
    .user-list__user-title {
      margin: 10px 0px;
    }
  }
}
</style>