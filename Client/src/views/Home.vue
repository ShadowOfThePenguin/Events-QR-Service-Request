<template>
  <div class="home" justify="center" align="center">
    <Report v-if='realRoom' :room='roomID' max-width='60%' />
    <Error404 v-if='!realRoom' :room='roomID' />
  </div>
</template>

<script>
import Error404 from "../components/404.vue"
import Report from "../components/Report.vue"
export default {
  name: "Home",
  components: {
    Error404,
    Report,
  },
  props: {
    roomID: String
  },
  computed: {
    realRoom() {
      window.console.log(this);
      window.console.log(this.$store.state.rooms);
      window.console.log(this.roomID);
      if(this.$store.state.rooms.includes(this.roomID)){
        return true
      } else {
        return false
      }
    }
  },
};
</script>
