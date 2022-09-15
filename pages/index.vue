<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <p v-if="$fetchState.pending">
        Loading
      </p>
      <SongCard
        v-for="(friend, index) in data"
        v-else
        :key="friend.user"
        :username="data[index].user.name"
        :song="data[index].track.name"
        :artist="data[index].track.artist.name"
        :imageurl="data[index].user.imageUrl"
        :songuri="data[index].track.uri"
      />
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'HomePage',
  data () {
    return {
      data: ''
      // data: { username: 'Jannes <3', songname: 'SOUL EATER', artist: 'TJ_beastboy', imageUrl: 'http://i.scdn.co/image/ab67616d0000b27357f937dcb5f763f90fa8f986', songUri: 'spotify:track:03egvWyPVBRkKLVIrJbkyR' }
    }
  },
  async fetch () {
    this.data = (await this.$axios.$get('https://friendify-client.vercel.app/api')).friends
  }
}
</script>
