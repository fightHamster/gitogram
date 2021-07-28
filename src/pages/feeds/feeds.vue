<template>
  <div class="header">
    <headline>
      <template #headline>
        <div class="top-icons-block">
          <div>
            <icon class="gitogram-icon" name="gitogramIcon"></icon>
          </div>
          <div class="top-right-icons-block">
            <icon class="home-icon" name="home"></icon>
            <icon class="photo-icon" name="photo"></icon>
            <icon class="exit-icon" name="exitBtn"></icon>
          </div>
        </div>
      </template>
      <template #content>
        <ul class="stories">
          <li class="stories-item" v-for="item in stories" :key="item.id">
            <story-user-item
              :avatar="item.avatar"
              :username="item.username"
              @onPress="handlePress(item.id)">
            </story-user-item>
          </li>
        </ul>
      </template>
    </headline>
  </div>
  <div class="content">
    <userPost v-for="post in posts" :key="post.id"
      :avatarUrl="post.avatar"
      :username="post.username"
      :articleName="post.articleName"
      :articleDesc="post.articleDesc"
      :comments="post.comments"></userPost>
  </div>
</template>

<script>
import { headline } from '../../components/headline'
import { icon } from '../../icons'
import { storyUserItem } from '../../components/storyUserItem'
import stories from './data.json'
import { userPost } from '../../components/userPost'
import posts from './posts.json'

export default {
  name: 'feeds',
  components: {
    headline,
    icon,
    storyUserItem,
    userPost
  },
  data () {
    return {
      stories,
      posts
    }
  }
}
</script>

<style lang="scss" src="./feeds.scss" scoped></style>
