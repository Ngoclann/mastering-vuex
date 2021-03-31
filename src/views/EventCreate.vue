<template>
  <div>
    <h1>Create an Event, {{ user.id }}</h1>
    <p>This event was created by {{ user.name }}</p>
    <ul>
      <li v-for="cat in categories" :key="cat">{{ cat }}</li>
    </ul>
    <p>There are {{ catLength }} categories</p>
    <p>There are {{ activeTodosCount }} things have not done yet</p>
    <p>{{ getEventById(1) }}</p>
  </div>
</template>

<script>
  import { mapState, mapGetters } from 'vuex'
  export default {
    computed: {
      // catLength() {
      //   return this.$store.getters.catLength
      // },
      ...mapGetters(['catLength', 'activeTodosCount', 'getEventById']),
      ...mapState(['user', 'categories'])
    }
  }
</script>

<style scoped>

</style>
