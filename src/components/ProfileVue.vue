<template>
  <Title :text="profileLabel" />
  <Paragraph :text="profile" />
</template>

<script>
import Title from "@/components/TitleVue.vue";
import Paragraph from "@/components/ParagraphVue.vue";

export default {
  name: "ProfileVue",

  components: { Title, Paragraph },

  computed: {
    currentLanguage() {
      return this.$store.state.currentLanguage;
    },

    profileLabel() {
      return this.currentLanguage.resumeLabels.profile;
    },

    profile() {
      return this.currentLanguage.data.profile;
    },
  },
};
</script>