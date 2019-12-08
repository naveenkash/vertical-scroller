<template>
  <div class="scroll-img">
    <img src="../assets/clock.png" alt />
    <img src="../assets/mobile.png" alt />
    <img src="../assets/laptop.png" alt />
    <img src="../assets/girl.png" alt />
  </div>
</template>
<script>
export default {
  name: "scrollimg",
  methods: {
    handleScroll() {
      var imgs = document.querySelectorAll(".scroll-img img");
      var nodes = Array.prototype.slice.call(imgs);
        var details = document.querySelectorAll(".scroll-info");
      for (let i = imgs.length - 1; i >= 0; i--) {
        var img = imgs[i];
        if (window.pageYOffset >= img.offsetTop) {
          var index = nodes.indexOf(img);//index of img and detail is same like img 2 will show the 2nd detail so if 2nd img is in view show 2nd detail
          for (let k = 0; k < details.length; k++) {
            const element = details[k];
            element.style.display = "none";//hide every detail except the detail index is sae to img
          }
          details[index].style.display = "flex"; //show the detail whose index is same as img
          return;
        }
      }
    }
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  }
};
</script>
<style lang="css">
.scroll-img {
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.scroll-img img {
  height: 730px;
  width: 600px;
  padding-top: 130px;
}
</style>