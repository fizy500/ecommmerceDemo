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
    <select v-model="selectedLocale" @change="changeLocale">
      <option v-for="locale in $i18n.locales" :key="locale.code" :value="locale.code">
        {{ locale.name }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedLocale: this.$i18n.locale, // Set initial locale
    };
  },
  methods: {
    changeLocale() {
      this.$i18n.setLocale(this.selectedLocale); // Dynamically change locale
    },
  },
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


