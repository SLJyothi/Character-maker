<template>
  <metainfo>
    <template v-slot:title="{ content }">{{
      content ? `${content} | AC: Character Maker` : 'AC: Character Maker'
    }}</template>
  </metainfo>
  <main class="main">
    <router-view></router-view>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useMeta } from 'vue-meta';

export default defineComponent({
  name: 'App',
  setup() {
    const title = 'AC: Character Maker';

    useMeta({
      title,
      'mobile-web-app-capable': {
        title
      },
      'apple-mobile-web-app-title': {
        title
      },
      htmlAttrs: {
        lang: 'en'
      }
    });
  }
});
</script>

<style lang="scss">
@use '@/styles/styles.scss' as *;

#app {
  @include size(100%, 100%);
  background-image: url('https://i.postimg.cc/9XLFnHgd/vecteezy-seamless-background-with-white-flowers-on-a-purple-background-7028679.png');
  background-size: cover;
  font-family: $font-primary;
  overflow: hidden;
  color: var(--accent-200);
}

.main {
  @include flex(center, space-between, column);
  @include size(100%, 100%);

  @media screen and (min-width: 1024px) {
    @include size(100%, 100vh);
    flex-direction: row;
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.15s;
}

.fade-enter,
.fade-leave-to

/* .fade-leave-active below version 2.1.8 */
  {
  opacity: 0;
}

// .appear {
//   opacity: 0;
//   transform: translate3d(0, 50%, 0);
//   animation: appear 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
//   @for $i from 1 through 100 {
//     &:nth-child(#{$i}) {
//       animation-delay: $i * 0.025s;
//     }
//   }
// }
// @keyframes appear {
//   0% {
//     opacity: 0;
//     transform: translate3d(0, 10%, 0);
//   }
//   100% {
//     opacity: 1;
//     transform: translate3d(0, 0, 0);
//   }
// }</style>
