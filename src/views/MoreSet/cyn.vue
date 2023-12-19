<template>
  <div class="listcards">
  <div class="listImgTitleFather ">
    <div class="avatar">
        <img class="avatar ch" @click="jumpTo" src="../../../public/images/icon/tks.jpg">
    </div>
    <h3 class="tks">特别鸣谢</h3>
      <div class="listTitleNormal">陈雅宁
      </div>
    <h4 class="listTitleNormalD">{{ info }}</h4>
    <h4 class="thing">{{ thing }}</h4>
  </div>
  </div>
</template>

<script>
// import axios from 'axios';

export default {
  data() {
    return {
      info:"女 2002年 山西大同",
      thing:"图标重绘",
    };
  },
};
</script>

<style lang="scss" scoped>

.ch{
  position:absolute;
  top:-10px;
  left: 0px;
}


.avatar {
  margin-top:10px;
  margin-bottom:10px;
}
</style>