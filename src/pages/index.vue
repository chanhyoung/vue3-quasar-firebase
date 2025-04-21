<template>
  <q-page padding>
    <div class="row q-col-gutter-x-lg">
      <PostLeftBar class="col-grow"></PostLeftBar>
      <section class="col-7">
        <PostHeader></PostHeader>
        <PostList :items="posts" />
      </section>
      <PostRightBar class="col-3"></PostRightBar>
    </div>
  </q-page>
</template>

<script setup>
import PostList from 'src/components/apps/post/PostList.vue';
import PostHeader from 'src/pages/components/PostHeader.vue';
import PostLeftBar from 'src/pages/components/PostLeftBar.vue';
import PostRightBar from 'src/pages/components/PostRightBar.vue';

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
</script>

<style lang="scss" scoped></style>
