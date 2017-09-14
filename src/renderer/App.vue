<template>
  <div id="app">
    <button @click="startServer">Start</button>
  </div>
</template>

<script>
  import LandingPage from '@/components/LandingPage'
  import {ipcRenderer} from 'electron'

  export default {
    name: 'electron-express',
    components: {
      LandingPage
    },
    methods: {
      startServer () {
        ipcRenderer.send('start')
        alert('check localhost:3000')
      }
    },
    created () {
    }
  }
</script>

<style>
  /* CSS */
</style>
