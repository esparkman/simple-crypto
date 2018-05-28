<template>
  <div class="ui top attached menu">
    <div class="item name">
      SimpleCrypto
    </div>
    <div class="ui icon item">
      <i class="home icon"></i>
    </div>
    <div class="ui icon item">
      <i class="question icon"></i>
    </div>
    <div class="right menu">
      <div class="ui right aligned category search item">
        <div class="ui transparent icon input">
          <v-select
            id="v-select"
            placeholder="Search..."
            :options="coins"
            label="name"
          ></v-select>
          <i class="search link icon"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'AppHeader',
  computed: {
    ...mapGetters(['coins'])
  }
}
</script>

<style src="@/assets/styles/app-header.css">
</style>

