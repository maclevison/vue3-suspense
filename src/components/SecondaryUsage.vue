<template>
  <div v-if="error">{{ error }}</div>
  <div v-else-if="users">
    <h2>Loaded the following users images</h2>

    <div class="users">
      <div class="user" v-for="user in users.data" :key="user.id">
        <img :src="user.avatar" :alt="`Avatar de ${user.first_name}`" />
      </div>
    </div>
  </div>
</template>

<script>
import useUsers from "../modules/users";

export default {
  name: "Users",

  setup() {
    const { users, error } = useUsers();

    return { users, error };
  },
};
</script>

<style scoped>
.users {
  padding: 8px;
  display: flex;
  flex-direction: row;
  width: 100%;
  justify-content: space-evenly;
  align-items: center;
}

.user {
  overflow: hidden;
  border-radius: 100%;
  height: 80px;
  width: 80px;
}

.user img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
