<template lang="html">
  <div class="columns vvb-margin">

    <div class="column is-8 is-offset-2">
      <h1>{{ vText }}</h1>
      <table class="table is-bordered is-striped is-narrow is-fullwidth">
        <thead>
          <tr>
            <th>ID</th>
            <th>Title</th>
            <th>Edit</th>

          </tr>
        </thead>
        <tbody>
          <tr v-for="user in adultUser">
            <th>
              {{ user.name }}
            </th>
            <th>
              {{ user.age }}
            </th>
            <th>
              <button class="button is-success" @click="adultIncrease" >increase</button>
              <button class="button is-danger" @click="adultDecrease">decrease</button>
            </th>
          </tr>

        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import {mapGetters, mapMutations} from 'vuex'
export default {
  name: 'VText',
  data () {
    return {
      vText: 'Vuex Mutations'
    }
  },
  computed: {
    ...mapGetters([
      'adultUser'
    ])
  },
  methods: {
    // adultIncrease () {
    //   this.$store.commit('adultIncrease')
    // }
    ...mapMutations([
      'adultIncrease',
      'adultDecrease'
    ])
  }
}
</script>

<style lang="css" scoped >

.vvb-margin{
  margin-top: 30px;
}
</style>
