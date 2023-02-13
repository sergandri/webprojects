<template>
  <div class="wrapper">
    <div class="header">
      <Header />
    </div>
    <div class="contacts">
      <ContactsVue />
    </div>
    <div class="profile">
      <ProfileVue />
    </div>
    <div class="skills">
      <Skills />
    </div>
    <div class="experience">
      <Experience />
    </div>
    <div class="education">
      <EducationVue />
    </div>
    <div class="expertise">
      <!-- <h3>EXPERTISE</h3> -->
    </div>
  </div>
</template>

<script>
import ContactsVue from "@/components/ContactsVue.vue";
import ProfileVue from "@/components/ProfileVue.vue";
import Header from "@/components/HeaderVue.vue";
import Skills from "@/components/SkillsVue.vue";
import Experience from "@/components/ExperienceVue.vue";
import EducationVue from "@/components/EducationVue.vue";

export default {
  name: "ResumeVue",

  components: { ContactsVue, ProfileVue, Header, Skills, Experience, EducationVue },
};
</script>

<style scoped>
.wrapper {
  display: grid;
  grid-template-columns: 1fr 3fr;
  grid-template-rows: 190px auto auto auto auto;
  grid-template-areas:
    "header header"
    "contacts profile"
    "skills experience"
    "education experience"
    "expertise experience";
}

.contacts,
.skills,
.education,
.expertise {
  padding: 0px 45px 0 45px;
  margin: 0px 0px 45px 0px;
}

.profile,
.experience {
  padding: 0px 45px 0 0;
  margin: 0px 0px 45px 0px;
}

.experience,
.expertise {
  margin: 0;
}

.header {
  display: flex;
  grid-area: header;
  background-image: url("~@/assets/wave.svg");
  background-repeat: no-repeat;
}

.contacts {
  grid-area: contacts;
}

.profile {
  grid-area: profile;
}

.skills {
  grid-area: skills;
}

.experience {
  grid-area: experience;
}

.education {
  grid-area: education;
}

.expertise {
  grid-area: expertise;
}

@media (max-width: 21cm) {
  .wrapper {
    grid-template-columns: 1fr;
    grid-template-rows: repeat(7, auto);
    grid-template-areas:
      "header"
      "contacts"
      "profile"
      "experience"
      "skills"
      "education"
      "expertise";
  }

  .header {
    background-image: url("~@/assets/wave-mobile.svg") !important;
  }

  .contacts,
  .skills,
  .profile,
  .experience,
  .expertise,
  .skills,
  .education {
    padding: 0px 20px 0 20px !important;
  }
}

@media print {
  .wrapper {
    grid-template-areas:
      "header header"
      "contacts profile"
      "skills experience"
      "education experience"
      "expertise experience";
  }
}
</style>