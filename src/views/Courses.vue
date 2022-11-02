<template>
  <v-container fluid class="mb-auto">
    <v-row dense>
      <v-col v-for="card in cards" :key="card.title" :cols="card.flex">
        <v-card>
          <v-img
            :src="card.src"
            class="white--text align-end"
            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            height="300px"
          >
            <v-card-title v-text="card.title"></v-card-title>
          </v-img>

          <v-card-actions>
            <v-spacer></v-spacer>

            <v-btn icon>
              <v-icon>mdi-heart</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>mdi-bookmark</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>mdi-share-variant</v-icon>
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    cards: [
      {
        title: "NICE COURSES HERE",
        src: "https://cdn.pixabay.com/photo/2017/01/14/13/59/castelmezzano-1979546__340.jpg",
        flex: 6,
      },
      {
        title: "ROAD TRIPS COURSES",
        src: "https://cdn.pixabay.com/photo/2015/05/18/23/53/backpacker-772991__340.jpg",
        flex: 6,
      },
      {
        title: "AIRLANES COURSES",
        src: "https://cdn.pixabay.com/photo/2020/03/03/20/31/boat-4899802__340.jpg",
        flex: 6,
      },
      {
        title: "AIRLANES COURSES",
        src: "https://cdn.pixabay.com/photo/2020/03/03/20/31/boat-4899802__340.jpg",
        flex: 6,
      },
      {
        title: "CYBER COURSES",
        src: "https://cdn.pixabay.com/photo/2017/03/23/09/34/artificial-intelligence-2167835__340.jpg",
        flex: 6,
      },
      {
        title: "CODING COURSES",
        src: "https://cdn.pixabay.com/photo/2015/09/09/21/12/monitor-933392__340.jpg",
        flex: 6,
      },
    ],
  }),
};
</script>
<style></style>
