<template>
  <div class="listcards">
  <div class="listImgTitleFather ">
    <div class="avatar" :style="{ 'background-image': `url(${avatarUrl})` }"></div>
    <h3 class="listTitle2">组员</h3>
      <div class="listTitleNormal">钟少斌
        <img class="hub ch" @click="jumpTo" src="../../../public/images/icon/github.png">
      </div>
    <h4 class="listTitleNormalD">{{ info }}</h4>
    <h4 class="thing">{{ thing }}</h4>
  </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      info:"男 2003年 山西忻州",
      thing:"优化、调试、组件开发",
      username: 'z013010',
      avatarUrl: ''
    };
  },
  mounted() {
    this.getAvatar();
  },
  methods: {
    jumpTo() {
      window.open('https://www.github.com/' + this.username);
    },
    getAvatar() {
      axios.get(`https://api.github.com/users/${this.username}`)
        .then(response => {
          this.avatarUrl = response.data.avatar_url;
        })
        .catch(error => {
          console.error('请求出错', error);
        });
    }
  }
};
</script>

<style lang="scss" scoped>

.ch{
  position:absolute;
  top:0px;
  left: 0px;
}

.hub {
  height: 24px;
  margin-left: 83px;
  margin-top: 3px;

  
}
.avatar {
  margin-top:10px;
  margin-bottom:10px;
}
</style>