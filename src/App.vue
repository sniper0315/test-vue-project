<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import TheWelcome from "./components/TheWelcome.vue";
</script>

<template>
  <header>
    <img
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <!-- <TheWelcome /> -->

    <p>Origin => 978014300723</p>
    <br />
    <p>Result => {{ checkISBN() }}</p>
  </main>
</template>

<script>
export default {
  methods: {
    checkISBN() {
      let isbn = "978014300723";
      let sum = 0;

      for (let i = 0; i < isbn.length; i += 1) {
        if (i % 2 === 0) sum += parseInt(isbn[i]) * 1;
        else sum += parseInt(isbn[i]) * 3;
      }

      let last = 10 - (sum % 10);

      if (last === 10) last = 0;

      return isbn + `${last}`;
    },
  },
};
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
