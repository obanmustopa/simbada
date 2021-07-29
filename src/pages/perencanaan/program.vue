<template>
  <div class="container">
    <div class="judul">
      <q-item-label header class="text-grey-10 q-pa-sx">
        <b>Daftar Program</b>
      </q-item-label>
    </div>
    <div class="tahun">
      <PilihTahun />
    </div>
    <div class="opd">
      <PilihOPD />
    </div>
    <div class="isinya">
      <div class="q-pa-md">
        <div class="q-gutter-y-md" style="max-width: 100%">
          <q-card>
            <q-tabs
              v-model="tab"
              dense
              class="text-grey"
              active-color="primary"
              indicator-color="primary"
              align="justify"
              narrow-indicator
            >
              <q-tab name="mails" label="Program" />
              <q-tab name="alarms" label="Kegiatan" />
              <q-tab name="movies" label="Sub-Kegiatan" />
            </q-tabs>

            <q-separator />

            <q-tab-panels v-model="tab" animated>
              <q-tab-panel name="mails">
                <div class="text-h6">Program</div>
                <div><aksi1 /></div>

                <ProgramList />
              </q-tab-panel>

              <q-tab-panel name="alarms">
                <div class="text-h6">Alarms</div>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
              </q-tab-panel>

              <q-tab-panel name="movies">
                <div class="text-h6">Movies</div>
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
              </q-tab-panel>
            </q-tab-panels>
          </q-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref, defineComponent } from "vue";
import PilihOPD from "components/PilihOPD.vue";
import PilihTahun from "components/PilihTahun.vue";
import ProgramList from "components/ProgramList.vue";
import aksi1 from "components/aksi1.vue";

export default defineComponent({
  components: { PilihOPD, PilihTahun, ProgramList, aksi1 },
  name: "Program",

  setup() {
    return {
      tab: ref("mails"),
    };
  },
});
</script>

<style scoped>
.container {
  display: grid;
  grid-auto-columns: 1fr;
  grid-auto-rows: 1fr;
  grid-template-columns: 14.5% 85.5%;
  grid-template-rows: 6.3% 0.2fr 2.7fr;
  gap: 1% 1%;
  grid-template-areas:
    "judul judul"
    "tahun opd"
    "isinya isinya";
}

.judul {
  grid-area: judul;
}

.tahun {
  grid-area: tahun;
}

.opd {
  grid-area: opd;
}

.isinya {
  grid-area: isinya;
}
</style>
