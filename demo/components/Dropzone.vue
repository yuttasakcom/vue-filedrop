<template>
  <div class="dropzone">
    <FileDrop multiple lazy processFiles readAs="DataURL">
      <FileBox slot-scope="{ files, clear }">
        <p v-if="!files.length">
          No images yet. Drop or click here to add some.
        </p>
        <div v-else>
          <ImagePreview width="150" />
          <button @click="handle(files, clear)">Save</button>
        </div>
      </FileBox>
    </FileDrop>
  </div>
</template>

<script>
export default {
  name: 'TypicalDropZone',
  methods: {
    handle(files, clear) {
      window.alert(`We have a file named ${files[0].name}`)
      clear()
    },
  },
}
</script>

<style scoped>
.dropzone {
  max-width: 550px;
  height: 200px;
  margin: 0 auto;
}
</style>
