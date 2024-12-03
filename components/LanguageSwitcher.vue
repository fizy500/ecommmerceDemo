<!-- <script setup lang="ts">
const { locales, locale, setLocale } = useI18n();

const language = computed({
  get: () => locale.value,
  set: (value) => {
    setLocale(value);
  },
});
</script>

<template>
  <div>Switch Language</div>
  <select v-model="language">
    <option
      v-for="item in locales"
      :key="typeof item === 'object' ? item.code : item"
      :value="typeof item === 'object' ? item.code : item"
    >
      {{ typeof item === "object" ? item.name : item }}
    </option>
  </select>
</template> -->




<template>
  <div class="language-switcher">
    <select v-model="$i18n.locale" @change="changeLocale($i18n.locale)">
      <option v-for="locale in $i18n.locales" :key="locale.code" :value="locale.code">
        {{ locale.name }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  methods: {
    changeLocale(locale) {
      this.$i18n.setLocale(locale); // Dynamically update the locale
    }
  }
};
</script>

<style scoped>
.language-switcher {
  margin: 16px 0;
}

select {
  padding: 8px 12px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 16px;
  cursor: pointer;
}
</style>

