<template>
  <button class="g-button" :class="{[`icon-${iconPosition}`]: true}">
    <g-icon class="loading" v-if="icon" name="loading"></g-icon>
    <g-icon class="icon" v-if="icon" :name="icon"></g-icon>
    <div class="content">
      <slot></slot>
    </div>
  </button>
</template>

<script>
  import GIcon from './icon'

  export default {
    name: 'GuaUIButton',
    components: {
      GIcon
    },
    props: {
      icon: {},
      iconPosition: {
        type: String,
        default: 'left',
        validator(value) {
          if (value !== 'left' && value !== 'right') {
            return false
          }
          return true
        }
      }
    }
  }
</script>

<style lang="scss" scoped>
  $font-size: 12px;
  $font-size-l: 14px;
  $font-size-ll: 16px;

  $button-border-radius: 14px;
  $button-border-radius-l: 16px;
  $button-border-radius-s: 11px;

  $button-height: 30px;

  $button-color: #666;
  $button-background-color: #f4f4f4;
  $button-border-color: #d9d9d9;
  $button-hover-color: #57c5f7;
  $button-hover-background-color: white;
  $button-hover-border-color: #57c5f7;
  $button-active-color: #2baee9;
  $button-active-background-color: white;
  $button-active-border-color: #2baee9;

  $primary-button-color: white;
  $primary-button-background-color: #2db7f5;
  $primary-button-border-color: #2db7f5;
  $primary-button-hover-color: white;
  $primary-button-hover-background-color: #57c5f7;
  $primary-button-hover-border-color: #57c5f7;

  $primary-button-active-color: #f2f2f2;
  $primary-button-active-background-color: #2baee9;
  $primary-button-active-border-color: #2baee9;

  @keyframes spin {
    0% { transform: rotate(0deg) }
    100% { transform: rotate(360deg) }
  }

  .g-button {
    box-sizing: border-box;
    transition: .3s cubic-bezier(.645, .045, .355, 1);
    font-size: var(--font-size); cursor: pointer; padding: 3px 12px;
    line-height: 1.5; font: inherit; border-radius: $button-border-radius;
    color: $button-color; border: 1px solid $button-border-color; background: $button-background-color;
    text-align: center; vertical-align: middle;
    display: inline-flex; justify-content: center; align-items: center;
    &, &:active, &:focus {
      outline: none;
    }
    .loading { animation: spin .3s infinite linear; }
    > .icon { order: 1; margin-right: .1em; }
    > .content { order: 2 }
    &.icon-right {
      > .icon { order: 2; margin-right: 0; margin-left: .1em; }
      > .content { order: 1 }
    }
    &.circle {
      width: 28px;
      height: 28px;
      padding: 0;
      border-radius: 50%;
    }

    &.lg {
      &.circle {
        width: 32px;
        height: 32px;
        padding: 0;
        font-size: $font-size-ll;
      }
      padding: 4px 15px 5px 15px;
      font-size: $font-size-l;
      border-radius: $button-border-radius-l;
    }
    &.sm {
      &.circle {
        width: 22px;
        height: 22px;
        padding: 0;
      }
      padding: 1px 7px;
      border-radius: $button-border-radius-s;
    }

    &.primary {
      color: $primary-button-color;
      border-color: $primary-button-border-color;
      background: $primary-button-background-color;
      svg { fill: white; }
      &:hover {
        svg { fill: $primary-button-hover-color; }
        color: $primary-button-hover-color;
        border-color: $primary-button-hover-border-color;
        background: $primary-button-hover-background-color;
      }
      &:active {
        svg { fill: $primary-button-active-color; }
        color: $primary-button-active-color;
        border-color: $primary-button-active-border-color;
        background: $primary-button-active-background-color;
      }
    }

    &.ghost {
      svg { fill: $button-color; }
      color: $button-color;
      border-color: $button-border-color;
      background: white;
    }

    &:hover {
      svg { fill: $button-hover-color; }
      color: $button-hover-color; border: 1px solid $button-hover-border-color; background: $button-hover-background-color;
    }

    &:active {
      svg { fill: $button-active-color; }
      color: $button-active-color;
      border: 1px solid $button-active-border-color;
      background: $button-active-background-color;
    }
    &.disabled, &.primary.disabled {
      color: #ccc;
      background-color: #f3f5f7;
      border-color: #d9d9d9;
      cursor: not-allowed;
    }
  }
</style>
