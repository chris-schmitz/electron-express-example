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
      }
    },
    created () {
      ipcRenderer.on('started', payload => {
        console.log(payload)
      })
    }
  }
</script>

<style>
  /* CSS */
</style>
