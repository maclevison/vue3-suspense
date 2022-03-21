<template>
  <div>{{ user.first_name }} {{ user.last_name }} - {{ user.email }}</div>
</template>

<script>
export default {
  name: "User",
  props: {
    user: Object,
  },
};
</script>
