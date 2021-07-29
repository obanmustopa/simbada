<template>
  <div class="q-pa-lg" style="padding-top: 20px; padding-bottom: 20px">
    <div>
      <q-fab
        v-model="fab1"
        label="Actions"
        label-position="top"
        external-label
        color="purple"
        icon="keyboard_arrow_right"
        direction="right"
        padding="xs"
      >
        <q-fab-action
          padding="5px"
          external-label
          label-position="top"
          color="primary"
          @click="onClick"
          icon="mail"
          label="Email"
        />
        <q-fab-action
          padding="5px"
          external-label
          label-position="top"
          color="orange"
          @click="onClick"
          icon="room"
          label="Map"
        />
      </q-fab>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    return {
      fab1: ref(false),
      fab2: ref(false),

      onClick() {
        // console.log('Clicked on a fab action')
      },
    };
  },
};
</script>
