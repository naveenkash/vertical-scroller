<template>
  <div class="scroll-info">
    <h1>{{info.head}}</h1>
    <p>{{info.para}}</p>
  </div>
</template>
<script>
export default {
  name: "scrolldetail",
  props: {
    info: Object
  },
  mounted() {
    var firstDetail = document.querySelector(".scroll-info");
    firstDetail.style.display = "flex";
  }
};
</script>
<style lang="css">
.scroll-info {
  padding-top: 130px;
  height: 730px;
  flex-direction: column;
  display: none;
  justify-content: center;
}
.scroll-info h1{
  font-size: 42px;
margin-bottom: 18px;
  color: black;
}
.scroll-info p{
  color: black;
  line-height: 30px;
}
</style>