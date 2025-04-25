<template>
  <q-page padding>
    <div class="row q-col-gutter-x-lg">
      <PostLeftBar class="col-grow"></PostLeftBar>
      <section class="col-7">
        <PostHeader></PostHeader>
        <PostList :items="posts" />
      </section>
      <PostRightBar
        class="col-3"
        @open-write-dialog="openWriteDialog"
      ></PostRightBar>
    </div>
    <PostWriteDialog v-model="openDialog" />
  </q-page>
</template>

<script setup>
import { ref } from 'vue';
import PostList from 'src/components/apps/post/PostList.vue';
import PostHeader from 'src/pages/components/PostHeader.vue';
import PostLeftBar from 'src/pages/components/PostLeftBar.vue';
import PostRightBar from 'src/pages/components/PostRightBar.vue';
import PostWriteDialog from 'src/components/apps/post/PostWriteDialog.vue';

import { useRouter } from 'vue-router';

const router = useRouter();
// const goPostDetails = id => router.push(`/posts/${id}`);

const posts = Array.from(Array(20), (_, index) => ({
  id: index,
  title: 'Vue3 Firebase 강의 ' + index,
  content:
    'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Autem, aut debitis perferendis porro hic nihil. Quaerat vel, id quae tempora aperiam minima ratione veniam eaque cum necessitatibus neque corporis eligendi?',
  readCount: 1,
  commentCount: 2,
  likeCount: 3,
  bookmarkCount: 4,
  tags: ['html', 'css', 'javascript'],
  uid: 'uid',
  category: '카테고리' + index,
}));

const openDialog = ref(false);
const openWriteDialog = () => {
  openDialog.value = true;
};
</script>

<style lang="scss" scoped></style>
