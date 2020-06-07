<template>
  <q-layout view="lHh Lpr lFf">
    <main-header/>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import header from 'components/header'

export default {
  components: {
    'main-header' : header
  },

  data () {
    return {
      elevateHeader: false
    }
  },
  computed: {
    elevated() {
      return this.elevateHeader
    }
  },
  methods: {
    scrolled(position) {
      if(position > 0) {
        this.elevateHeader = !this.elevateHeader;
      }
    }
  }
}
</script>
