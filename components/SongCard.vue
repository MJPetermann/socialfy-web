<template>
  <v-card
    class="rounded-xl mt-2"
    plain
    light
  >
    <v-list-item three-line>
      <v-list-item-content>
        <div class="text-overline mb-4">
          {{ username }}
        </div>
        <v-list-item-title class="text-h5 mb-1">
          {{ song }}
        </v-list-item-title>
        <v-list-item-subtitle>{{ artist }}</v-list-item-subtitle>
      </v-list-item-content>

      <v-list-item-avatar
        tile
        size="80"
        color="grey"
      >
        <img
          v-if="imageurl"
          :src="imageurl"
          alt="Profile Picture"
        >
      </v-list-item-avatar>
    </v-list-item>
    <v-card-actions>
      <v-btn
        outlined
        rounded
        text
        :href="songurl"
      >
        Hear it yourself
      </v-btn>
    </v-card-actions>
  </v-card>
</template>
<script>
export default {
  props: {
    // eslint-disable-next-line vue/require-default-prop, vue/require-prop-types
    username: String, song: String, artist: String, imageurl: String, songuri: String

  },
  data () {
    return {
      songurl: 'https://open.spotify.com/track/' + this.songuri.split(':')[2]

    }
  },
  methods: {
    showList () {
      this.show = true
    }
  }
}
</script>
