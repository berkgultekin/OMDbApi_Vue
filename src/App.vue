<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
}

html {
  font-size: 62.5%;
}

body {
  background-image: url('./assets/background.jpg');
  background-size:cover;
  margin: 0;
}

h1,
h2,
h3,
h4,
h5,
p,
span {
  color: white;
}

input,
button,
select,
a {
  outline: none;
}

a {
  text-decoration: none;
}

.btn {
  font-family: "Montserrat", sans-serif;
  font-size: 2.2rem;
  font-weight: 500;
  color: white;
  background: #f40048;
  text-transform: uppercase;
  border: none;
  cursor: pointer;

  &:hover {
    box-shadow: 0px 0px 30px #f40048;
  }
}

input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

input[type="number"] {
  -moz-appearance: textfield;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
  color: white;
}
</style>
