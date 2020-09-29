<template>
  <div>
    <p>Select Locale</p>
    <select v-model="$i18n.locale" style="">
      <option v-for="(value, index) in langs" :key="index" :value="value">
        {{ value }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "LocaleSelector",
  data() {
    return { langs: ["en", "fr", "ja"] };
  },
};
</script>
