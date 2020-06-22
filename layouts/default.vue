<template>
  <div class="wrapper">
    <nuxt-link class="logo" to="/">Nuxt blog starter</nuxt-link>
    <nuxt />
  </div>
</template>

<style>
html {
  font-family: "Arial", sans-serif;
  font-size: 16px;
  box-sizing: border-box;
}

p {
  margin-bottom: 10px;
}

.logo {
  font-weight: bold;
  text-align: center;
  display: block;
  color: black;
  font-size: 20px;
  margin: 0 0 2rem 0;
  text-decoration: none;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.wrapper {
  max-width: 720px;
  margin: 0 auto;
  padding: 2rem;
}
</style>
