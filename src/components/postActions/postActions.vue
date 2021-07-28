<template>
  <div class="post-actions">
    <button class="post-actions-item bg--gray"><icon class="btnWithCount" name="btnWithCount"></icon>Star</button>
    <button class="post-actions-item text-hover">156k</button>
    <button class="post-actions-item bg--gray"><icon class="fork" name="fork"></icon>Fork</button>
    <button class="post-actions-item text-hover">4</button>
  </div>
</template>

<script>
import { icon } from '../../icons'
export default {
  name: 'postActions',
  components: {
    icon
  }
}
</script>

<style lang="scss" src="./postActions.scss" scoped></style>
