<script>
import UserCard from "../src/components/UserCard.vue"
export default {
  component: {
    UserCard
  },
  data() {
    return {
      userData: {}
    }
  },
  methods: {
    async getData(){
      try {
        const res = await fetch("https://dummyjson.com/users/1")
        if(res.status === 200){
          const user = await res.json()
          this.userData = user.data
        }
      } catch (error) {
        console.log(error)
      }
    }
  },
  watch: {},
  mounted() {
  },
}
</script>

<template>
    <div class="container grid grid-cols-4">
      <UserCard :user="userData">
    </div>
</template>

<style>

</style>
