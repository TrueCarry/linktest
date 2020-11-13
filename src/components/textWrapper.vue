<template>
  <div class="text__wrapper">
    <div
      v-for="(token, i) in tokens"
      :key="i"
    >
      <span
        v-if="false"
        v-text="'123'"
      />

      <div v-else-if="token.type === 'mention'">
        BeforeCE <custom-element>f</custom-element> AfterCE
      </div>
    </div>
  </div>
</template>

<script>
import CustomElement from './CustomElement.vue'

export default {
  components: {
    CustomElement,
  },

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
