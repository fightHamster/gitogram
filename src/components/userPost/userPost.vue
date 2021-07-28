<template>
  <div class="post">
    <articleAuthor :avatar="avatarUrl" :author="username"></articleAuthor>
    <userArticle>
      <template #article>
        <div class="article-name">
          {{ articleName }}
        </div>
        <div class="article-desc">
          {{ articleDesc }}
        </div>
        <postActions></postActions>
      </template>
    </userArticle>
    <toggler @onToggle="toggle"></toggler>
    <div class="comments" v-if="shown">
      <ul class="comments-list">
        <li class="comments-item" v-for="comment in comments" :key="comment.id">
          <comment :text="comment.text" :username="comment.username"></comment>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import { toggler } from '../toggler'
import { comment } from '../comment'
import { userArticle } from '../userArticle'
import { articleAuthor } from '../articleAuthor'
import { postActions } from '../postActions'

export default {
  name: 'userPost',
  components: {
    toggler,
    comment,
    userArticle,
    articleAuthor,
    postActions
  },
  data () {
    return {
      shown: true
    }
  },
  props: {
    username: {
      type: String,
      required: true
    },
    avatarUrl: {
      type: String,
      required: true
    },
    articleName: {
      type: String,
      required: true
    },
    articleDesc: {
      type: String,
      required: true
    },
    comments: {
      type: Array,
      required: true
    }
  },
  methods: {
    toggle (isOpened) {
      this.shown = isOpened
    }
  }
}
</script>

<style lang="scss" src="./userPost.scss" scoped></style>
