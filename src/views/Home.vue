<template>
  <v-app>
    <vue-headful title="CV Kensuke Mitsuzawa" description=" " />
    <HeaderBar></HeaderBar>
    <v-main>
      <v-layout text-xs-center px-3 py-3 row wrap>
        <v-flex>
          <v-row align="center" justify="center">
            <v-col cols="auto">
              <v-img
              max-width="500"
              max-height="600"
              src="https://github.com/Kensuke-Mitsuzawa/Kensuke-Mitsuzawa.github.io/blob/master/images/profile_photo.jpg?raw=true"></v-img>
            </v-col>
          </v-row>
          <v-row align="center" justify="center">
            <v-col cols="auto">
              <button @click="changeLocaleToEn">
                <country-flag country="gb" size="normal" />
              </button>
              <button @click="changeLocaleToJa">
                <country-flag country="jp" size="normal" />
              </button>
              <button @click="changeLocaleToDe">
                <country-flag country="de" size="normal" />
              </button>
            </v-col>
          </v-row>
        </v-flex>
      </v-layout>

      <AbstractSection></AbstractSection>
      <v-divider></v-divider>
      <DigitalSkills></DigitalSkills>
      <v-divider></v-divider>
      <Languages></Languages>
      <v-divider></v-divider>
      <Education></Education>
      <v-divider></v-divider>
      <WorkExperience></WorkExperience>
      <v-divider></v-divider>
      <Contact></Contact>
      <router-view />
    </v-main>
    <v-footer color="black" dark app></v-footer>
  </v-app>
</template>

<script>
import AbstractSection from '@/views/Abstract';
import DigitalSkills from '@/views/DigitalSkills';
import Languages from '@/views/Languages';
import Education from '@/views/Education';
import WorkExperience from '@/views/WorkExperience';
import Contact from '@/views/Contact';
import HeaderBar from '@/views/HeaderBar';

export default {
  name: 'App',
  components: {
    AbstractSection,
    DigitalSkills,
    Languages,
    Education,
    WorkExperience,
    Contact,
    HeaderBar,
  },
  data() {
    return {
      drawer: null,
      feed_name_objects: [],
      loading: true,
      signedIn: false,
    };
  },
  created() {},
  mounted() {
    setTimeout(() => {
      this.loading = false;
    }, 1000);
  },
  methods: {
    changeLocaleToJa: function() {
      this.$i18n.locale = 'jp';
    },
    changeLocaleToEn: function() {
      this.$i18n.locale = 'en';
    },
    changeLocaleToDe: function() {
      this.$i18n.locale = 'de';
    },
  },
};
</script>
