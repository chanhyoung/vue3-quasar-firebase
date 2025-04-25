<template>
  <StickySiceBar>
    <q-card flat bordered>
      <q-list bordered separator>
        <q-item clickable v-ripple :active="true">
          <q-item-section>전체</q-item-section>
        </q-item>
        <q-item v-for="cate in categories" :key="cate.value" clickable v-ripple>
          <q-item-section>{{ cate.label }}</q-item-section>
        </q-item>
      </q-list>
    </q-card>
  </StickySiceBar>
</template>

<script setup>
import StickySiceBar from 'src/components/StickySideBar.vue';
import { getCategories } from 'src/services/category';

const categories = getCategories();
</script>

<style lang="scss" scoped></style>
