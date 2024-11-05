<template>
  <Mug>
    <Cold v-if="isIced" />
    <Hot v-else />
    <Contents>
      <template v-slot:top>
        <Creamer v-if="creamer.name !== 'No Cream'" :color="creamer.color" />
      </template>
      <template v-slot:mid>
        <Syrup v-if="syrup.name !== 'No Syrup'" :color="syrup.color" />
      </template>
      <template v-slot:bottom>
        <Base :color="base.color" />
      </template>
    </Contents>
  </Mug>
</template>
<script setup lang="ts">
import Contents from "./Contents.vue";
import Mug from "./Mug.vue";
import Syrup from "./Syrup.vue";
import Base from "./Base.vue";
import Creamer from "./Creamer.vue";
import Hot from "./Hot.vue";
import Cold from "./Cold.vue";

type Props = {
  isIced: boolean;
  base: { color: string };
  creamer: { color: string; name: string };
  syrup: { color: string; name: string };
};
defineProps<Props>();
</script>
