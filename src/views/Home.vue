<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <h1>{{ joke }}</h1>
    <h1>{{ joke2 }}</h1>
  </div>
</template>

<style></style>

<script>
export default {
  data: function () {
    return {
      message:
        "My town is super well known now because of this well-known cartographer that grew up here. He really put us on the map!",
      joke: "Why was the scarecrow awarded a medal? Becuase he was outstanding in his field.",
      joke2: "What did the bison say to his son when he went to school? 'Bison!'",
    };
  },
  created: function () {},
  methods: {},
};
</script>
