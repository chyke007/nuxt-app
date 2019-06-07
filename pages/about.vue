<template>
  <div>
    <h1> About Me</h1>
    <p>This is an app that displays dad jokes</p>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "About the App",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for dad jokes"
        }
      ]
    };
  }
};
</script>

<style>
</style>
