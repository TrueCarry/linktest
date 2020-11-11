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
        v-if="token.type === 'text'"

        v-text="token.value"
      />

      <a
        v-else-if="token.type === 'url'"
        :href="token.href"
        target="_blank"
        rel="noopener"
        v-text="token.value"
      />

      <div v-else-if="token.type === 'mention'">
        <nuxt-link
          to="/aaa"
        >
          123
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>

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
