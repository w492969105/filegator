<template>
  <div>
    <div class="modal-card">
      <header class="modal-card-head">
        <p class="modal-card-title">{{ currentItem.name }}</p>
      </header>
      <section class="modal-card-body preview">
        <video controls :src="videoSrc(currentItem.path)" class="video-player"></video>
      </section>
      <footer class="modal-card-foot">
        <button class="button" type="button" @click="$parent.close()">
          {{ lang('Close') }}
        </button>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: 'VideoPlayer',
  props: ['item'],
  data() {
    return {
      currentItem: this.item,
    }
  },
  methods: {
    videoSrc(path) {
      return this.getDownloadLink(path)
    },
  },
}
</script>

<style scoped>
.modal-card {
  width: 100%;
  min-width: 640px;
}
.preview {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 450px;
}
.video-player {
  max-width: 100%;
  max-height: 100%;
}
</style>