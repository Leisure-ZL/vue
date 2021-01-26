<template>
  <div id="app">
    <!-- <TodoList /><br>
    <Calendar />
    <Avatar />
    <Test /> 
    <PrivacyPage />-->
    <Rotate />
  </div>
</template>

<script>
// import TodoList from "./components/TodoList.vue"
// import Test from "./components/Test.vue"
// import Calendar from "./components/Calendar.vue"
// import Avatar from "./components/Avatar.vue"
// import PrivacyPage from "./components/PrivacyPage.vue"
import Rotate from "./components/Rotate.vue"
export default {
  name: 'App',
  components: {
    // PrivacyPage
    // TodoList,
    // Test,
    // Calendar,
    // Avatar
    Rotate
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
