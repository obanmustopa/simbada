<template>
  <div class="q-pa-md" style="max-width: 950px">
    <div class="q-gutter-xs">
      <q-select
        filled
        v-model="model"
        :options="options"
        stack-label
        label="Pilih OPD"
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
import axios from "axios";
import { onMounted, ref } from "vue";

export default {
  setup() {
    let options = ref([]);
    onMounted(() => {
      axios
        .get("http://localhost/simbada_api/unit_list.php")
        .then((result) => {
          options.value = result.data;
        })
        .catch((err) => {
          console.log(err.response);
        });
    });
    return {
      model: ref({
        label: "OPD",
        value: "",
        icon: "mail",
      }),
      options,
    };
  },
};
</script>
