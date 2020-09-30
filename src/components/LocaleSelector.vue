<template>
  <q-select
    v-model="$i18n.locale"
    :options="options"
    :label="$t('lang')"
    bg-color="white"
    outlined
    dense
  />
</template>

<script>
export default {
  name: "LocaleSelector",

  props: {
    options: { type: Array },
  },
};
</script>
