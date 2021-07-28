<template>
  <div class="author-block">
    <img :src="avatar" class="author-icon" />
    <span class="nickname">{{ author }}</span>
  </div>
</template>

<script>
export default {
  name: 'articleAuthor',
  props: {
    author: {
      type: String,
      required: true
    },
    avatar: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" src="./articleAuthor.scss" scoped></style>
