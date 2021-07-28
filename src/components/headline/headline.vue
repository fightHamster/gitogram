<template>
  <div class="c-header">
    <div class="ex_container">
      <div class="headline">
        <slot name="headline"></slot>
      </div>
      <div class="content" v-if="$slots.content">
        <slot name="content"></slot>
      </div>
    </div>
  </div>
</template>

<style lang="scss" src="./headline.scss" scoped></style>
