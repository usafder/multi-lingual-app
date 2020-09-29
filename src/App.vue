<template>
  <div id="app">
    <LocaleSelector />
    <h1>{{ $t("hello") }}</h1>
  </div>
</template>

<script>
import LocaleSelector from "./components/LocaleSelector";

export default {
  name: "App",
  components: { LocaleSelector },
};
</script>

<style>
#app {
  text-align: center;
}
</style>
