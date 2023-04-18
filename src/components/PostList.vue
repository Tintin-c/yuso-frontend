<template>
  <a-list item-layout="horizontal" :data-source="props.postList">
    <template #renderItem="{ item }">
      <a-list-item>
        <a-list-item-meta>
          <template #description>
            <p v-html="item.content"></p>
          </template>
          <template #title
          ><a href="https://www.antdv.com/" v-html="item.title"></a></template>
          <template #avatar>
            <a-avatar :src="gege"/>
          </template>
        </a-list-item-meta>
      </a-list-item>
    </template>
  </a-list>
</template>

<script setup lang="ts"> import gege from "../assets/avatar.jpg";
import { withDefaults, defineProps } from "vue";

interface Post {
  title: string;
  content: string;
}

interface Props {
  postList: Post[];
}

const props = withDefaults(defineProps<Props>(), {postList: () => [] as Post[],}); </script>
<style scoped> .gege {
  width: 200px;
} </style>