<template>
  <div class="main">
    <crossBallMenu></crossBallMenu>
    <main>
      <div class="persona">
        <personDetails></personDetails>
      </div>
      <div class="stat-wrapper">
        <statistics></statistics>
        <tableScore></tableScore>
      </div>
    </main>
    <theFooter></theFooter>
  </div>
</template>

<script>
import CrossBallMenu from '../components/CrossBallMenu.vue'
import TableScore from '../components/TableScore.vue'
import Statistics from '../components/Statistics.vue'
import PersonDetails from '../components/PersonDetails.vue'
import TheFooter from '../components/Footer.vue'

export default {
  components: {
    CrossBallMenu,
    TableScore,
    Statistics,
    PersonDetails,
    TheFooter
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.main {
  background-color: #faf9f9;
  display: flex;
  flex-direction: column;
}
main {
  display: flex;
}
.stat-wrapper {
  display: flex;
  flex-direction: column;
}
.persona {
}
</style>
