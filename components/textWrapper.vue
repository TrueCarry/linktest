<template>
  <div class="text__wrapper">
    <nuxt-link to="bbb">
      TestLink
    </nuxt-link>
    <div
      v-for="(token, i) in tokens"
      :key="i"
    >
      <span
        v-if="false"
        v-text="'123'"
      />

      <div v-else-if="token.type === 'mention'">
        <CustomElement />
      </div>
    </div>
  </div>
</template>

<script>
import CustomElement from './CustomElement.vue'

export default {
  props: {
    text: {
      type: String,
      default: '',
    },
  },

  computed: {
    tokens () {
      return [{ type: 'mention', href: 'cats', value: '@cats' }]
    },
  },
}
</script>
