<template>
  <div class="q-pa-md" style="max-width: 300px">
    <div class="q-gutter-md">
      <q-select
        filled
        v-model="model"
        :options="options"
        stack-label
        label="Tahun"
        color="secondary"
      >
        <template v-slot:selected-item="scope">
          <q-chip
            removable
            dense
            @remove="scope.removeAtIndex(scope.index)"
            :tabindex="scope.tabindex"
            color="white"
            text-color="secondary"
            class="q-ma-none"
          >
            <q-avatar
              color="secondary"
              text-color="white"
              :icon="scope.opt.icon"
            />
            {{ scope.opt.label }}
          </q-chip>
        </template>
      </q-select>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    return {
      model: ref({
        label: "tahun",
        value: "goog",
        icon: "mail",
      }),

      options: [
        {
          label: "2021",
          value: "2021",
          icon: "mail",
        },
        {
          label: "2022",
          value: "2022",
          icon: "bluetooth",
        },
        {
          label: "2022",
          value: "2022",
          icon: "map",
        },
        {
          label: "2024",
          value: "2022",
          icon: "golf_course",
        },
        {
          label: "2025",
          value: "2022",
          // disable: true,
          icon: "casino",
        },
      ],
    };
  },
};
</script>
