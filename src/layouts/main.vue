<template>
  <q-layout view="hhr lpR fFf">
    <!-- <q-header reveal class="bg-primary">
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleDrawer"
        />

        <q-toolbar-title>
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="drawerOpen"
      side="right"
      elevated
      overlay
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
        </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer> -->
    
    <q-page-container>
      <router-view />
    </q-page-container>
    <LayoutFooter></LayoutFooter>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
// import EssentialLink from 'src/components/layouts/link.vue'
import LayoutFooter from "src/components/layouts/footer.vue";

const linksList = [];

export default defineComponent({
  name: 'layouts-mainLayout',

  components: {
    // EssentialLink,
    LayoutFooter,
  },

  setup () {
    const drawerOpen = ref(false);

    const toggleDrawer = () => {
      drawerOpen.value = !drawerOpen.value;
    };

    return {
      essentialLinks: linksList,
      drawerOpen,
      toggleDrawer,
    }
  }
})
</script>

