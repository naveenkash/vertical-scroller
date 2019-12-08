<template>
  <div class="scroll">
    <div class="scroll-container">
      <div class="scroll-detail-wrapper" :class="{fixed:scrolled,'align-down':scrolledToBottom}">
        <Scroll v-for="(info,index) in detail" :key="index" :info="info" />
      </div>
      <div class="scroll-image-wrapper">
        <ScrollImage />
      </div>
    </div>
  </div>
</template>
<script>
import Scroll from "./scrollDetail";
import ScrollImage from "./scrollImage";
export default {
  name: "scrollmain",
  components: {
    Scroll,
    ScrollImage
  },
  data() {
    return {
      scrolled: false,
      scrolledToBottom: false,
      detail: [
        {
          head: "Lorem Ipsum is simply dummy text 1",
          para:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,"
        },
        {
          head: "Lorem Ipsum is simply dummy text 2",
          para:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,"
        },
        {
          head: "Lorem Ipsum is simply dummy text 3",
          para:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,"
        },
        {
          head: "Lorem Ipsum is simply dummy text 4",
          para:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,"
        }
      ]
    };
  },
  methods: {
    handlePosition() {
      var scrollContainer = document.querySelector(".scroll-container");
      var scrollDetail = document.querySelector(".scroll-detail-wrapper")
        .children;
      var style =
        scrollDetail[scrollDetail.length - 1].currentStyle ||
        window.getComputedStyle(scrollDetail[scrollDetail.length - 1]);

      if (style.display == "flex") {
        this.scrolled = false;
        this.scrolledToBottom = true;
      } else if (window.pageYOffset >= scrollContainer.offsetTop) {
        this.scrolled = true;
        this.scrolledToBottom = false;
      } else {
        this.scrolledToBottom = false;
        this.scrolled = false;
      }
    }
  },
  mounted() {
    window.addEventListener("scroll", this.handlePosition);
  }
};
</script>
<style lang="css">
.scroll {
  width: 1150px;
  margin: 0 auto;
  height: auto;
  padding-bottom: 150px;
  margin-bottom: 80px;
}
.scroll-detail-wrapper {
  width: 500px;
  height: auto;
}
.align-down {
  display: flex;
  align-items: flex-end;
}
.scroll-image-wrapper {
  width: 600px;
  height: auto;
  margin-left: auto;
}
.scroll-container {
  display: flex;
  height: auto;
  justify-content: space-between;
}
</style>