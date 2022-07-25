<template>
  <div>
    <input ref="file" type="file" accept=".txt" style="display: none" @change="uploadFile()">
    <v-btn @click="uploadClick()" block>Upload file</v-btn>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'FileUpload',

  emits: [
    'upload'
  ],

  setup (props, { emit }) {
    const file = ref(null)

    const uploadClick = () => {
      file.value.click()
    }

    const uploadFile = () => {
      const f = file.value.files[0]
      const reader = new FileReader()
      reader.onload = (e) => {
        emit('upload', e.target.result)
      }
      reader.readAsText(f)
    }

    return {
      file,
      uploadClick,
      uploadFile
    }
  }
}
</script>
