<template>
  <q-layout>
    <q-header elevated>
      <q-toolbar>
        <q-btn flat dense round icon="menu" @click="onDrawerMenuClicked" />

        <q-toolbar-title>Multilingual App</q-toolbar-title>

        <div class="col-xs-3 col-sm-2 col-md-1">
          <locale-selector :options="langs"></locale-selector>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="isDrawerVisible" bordered>
      <q-scroll-area class="fit">
        <q-list padding>
          <template v-for="item in drawerMenuItems">
            <q-item
              :active="activeItem === item.label"
              clickable
              v-ripple
              :key="item.label"
              @click="activeItem = item.label"
            >
              <q-item-section avatar>
                <q-icon :name="item.icon" />
              </q-item-section>

              <q-item-section>{{ $t(item.label) }}</q-item-section>
            </q-item>
          </template>
        </q-list>
      </q-scroll-area>
    </q-drawer>

    <q-page-container>
      <h4 class="text-center">
        {{ $t("message", { pageName: $t(activeItem) }) }}
      </h4>
    </q-page-container>
  </q-layout>
</template>

<script>
import LocaleSelector from "./components/LocaleSelector";

export default {
  name: "App",

  components: {
    LocaleSelector,
  },

  data() {
    return {
      isDrawerVisible: true,
      langs: ["en", "fr", "ja"],
      drawerMenuItems: [
        { icon: "home", label: "drawerMenu.home" },
        { icon: "info", label: "drawerMenu.about" },
        { icon: "phone", label: "drawerMenu.contact" },
      ],
      activeItem: "drawerMenu.home",
    };
  },

  methods: {
    onDrawerMenuClicked() {
      this.isDrawerVisible = !this.isDrawerVisible;
    },
  },
};
</script>
