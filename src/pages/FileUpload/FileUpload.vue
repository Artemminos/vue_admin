<template>
  <div id="app">
    <div>
      <h2>Select an image</h2>
      <input multiple accept="image/jpeg,image/png" type="file" @change="onFileChange">
    </div>

    <template v-for="item in imageArr" :key="item.name">
      <img :src="item.url" width="200" height="200" :alt="item.name">
    </template>
  </div>
</template>

<script>


export default {
  data: function () {
    return {
      image: '',
      imageArr: []
    };
  },
  methods: {
    onFileChange(e) {
      let files = e.target.files || e.dataTransfer.files;
      if (!files.length) return;
      this.createIMG(files);
    },
    createImage(file) {
      let reader = new FileReader();
      let vm = this;
      reader.onload = (e) => {
        vm.image = e.target.result;
      };
      reader.readAsDataURL(file);
    },
    createIMG(files) {
      files.forEach(e => {
        this.imageArr.push(
            {
              name: e.name,
              url: URL.createObjectURL(e)
            }
        )
      })
    },
  }
}
</script>


