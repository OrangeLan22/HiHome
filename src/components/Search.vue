<template>
  <div class="search-box">
    <input class="input" v-model="inputValue" :placeholder="message">
    <button v-if="isSearching" @click="search()" >搜 索</button>
  </div>
  <!-- 其他内容 -->
</template>

<script>
export default {
    data() {
        return {
        message : "搜索一下",
        inputValue: '',
        isSearching: false,
        }
    },
    methods: {
        search() {
        console.log("搜索关键字：" + this.inputValue);
        window.open('https://www.baidu.com/s?wd=' + this.inputValue);
        }
    },
    watch:{
        inputValue(newVal){
            if (newVal.trim().length > 0){
                this.isSearching = true;
            }
            else{
                this.isSearching = false;
            }
        }
    },
    }
</script>

<style lang="scss" scoped>
.search-box {
    align-items: center;
    display: flex;
    padding: 1rem;
    margin-top: 2rem;
    margin-bottom:2rem ;
    max-width: 460px;
    animation: fade 0.5s;

    @media (max-width: 720px) {
        max-width: 100%;
      }
    @media (max-width: 390px) {
      .search-box {
        margin-top: 2.5rem;
      }
    }
}
</style>