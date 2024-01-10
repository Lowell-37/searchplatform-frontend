<template>
  <a-list
    item-layout="horizontal"
    :grid="{ gutter: 16, xs: 1, sm: 2, md: 4, lg: 4, xl: 6, xxl: 3 }"
    :data-source="props.userList"
  >
    <template #renderItem="{ item }">
      <a-list-item>
        <a-card hoverable style="width: 240px">
          <template #cover>
            <img alt="example" :src="mountain" />
          </template>
          <a-card-meta :title="item.userName">
            <template #description> {{ item.userProfile }}</template>
          </a-card-meta>
        </a-card>
      </a-list-item>
    </template>
  </a-list>
</template>

<script setup lang="ts">
import mountain from "../assets/mountain.jpg";
import { defineProps, withDefaults } from "vue";

interface Props {
  userList: never[];
}

const props = withDefaults(defineProps<Props>(), {
  userList: () => [],
});
</script>
<style scoped>
.mountain {
  width: 200px;
}
</style>