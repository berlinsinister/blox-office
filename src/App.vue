<template>
  <SingleOffice />
</template>

<script>
import SingleOffice from "./components/SingleOffice.vue";

export default {
  name: "App",
  components: {
    SingleOffice,
  },
};
</script>

<style>
@font-face {
  font-family: "FiraGO";
  src: local("FiraGO"),
    url("./assets/fonts/FiraGO-Regular.ttf") format("truetype");
}
@font-face {
  font-family: "Adieu";
  src: local("Adieu"), url("./assets/fonts/Adieu-Bold.ttf") format("truetype");
}
@font-face {
  font-family: "Gotham";
  src: local("Gotham-Book"),
    url("./assets/fonts/Gotham-Book.ttf") format("truetype");
}

*,
*:before,
*:after {
  box-sizing: border-box;
}

body {
  background: #f3f3f3;
}
</style>