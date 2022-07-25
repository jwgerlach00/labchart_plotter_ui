<template>
  <v-container>
    <v-row justify="center">
      <v-col cols="12">
        <link rel="stylesheet" type="text/css" href="//fonts.googleapis.com/css?family=Varela+Round"/>
        <h1>Labchart Plotter</h1>

        <v-card>
          <v-row justify="center">
            <v-col cols="4">
              <file-upload @upload="ape($event)"/>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import FileUpload from '../components/FileUpload.vue'

export default {
  name: 'HomeView',
  components: {
    'file-upload': FileUpload
  },

  setup () {
    const ape = (data) => {
      console.log(data)
    }

    return {
      ape
    }
  }
}
</script>

<style scoped>
h1 {
  font-family: "Varela Round" !important;
  color: rgb(100, 200, 150);
  font-size: 4vw;
  text-align: center;
}
</style>
