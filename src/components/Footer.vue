<template>
  <v-footer color="blue-grey darken-4 " min-height="100px" app padless>
    <v-row justify="center" no-gutters>
      <v-btn
        v-for="link in links"
        :key="link"
        color="white"
        text
        rounded
        class="my-2"
      >
        {{ link }}
      </v-btn>
      <v-col class="blue-grey darken-4 py-4 text-center white--text" cols="12">
        &copy; {{ new Date().getFullYear() }} —
        <strong>Courses Franc_pro </strong>
      </v-col>
    </v-row>
  </v-footer>
</template>
<script>
export default {
  data: () => ({
    links: ["Home", "About Us", "Team", "Services", "Blog", "Contact Us"],
  }),
};
</script>
