<template>
  <section class="main-search">
    <form method="get" class="search-nav" action="https://cn.bing.com/search" target="_blank" ref="search">
      <input type="text" name="q" ref="btn" class="search-control" placeholder="搜索一下"/>
      <input type="submit" class="search-submit" value="搜索">
    </form>
  </section>
  <div class="search-button">
    <button class="search-btn" id="bing" @click="searchClickb()">
      必应
    </button>
    <button class="search-btn" id="google" @click="searchClickg()">
      谷歌
    </button>
    <button class="search-btn" id="baidu" @click="searchClickd()">
      百度
    </button>
    <button class="search-btn" id="zhihu" @click="searchClickz()">
      知乎
    </button>
    <button class="search-btn" id="bilibili" @click="searchClickbi()">
      B站
    </button>
    <button class="search-btn" id="juejin" @click="searchClickj()">
      掘金
    </button>
  </div>
</template>

<script>
export default {
  name: 'Search',
  watcher:{

  },
  methods:{
    searchClickb(){
      this.$refs.search.action = 'https://cn.bing.com/search'
      this.$refs.btn.name = 'q'
      this.$refs.btn.placeholder = '必应一下'
      this.$refs.btn.value = ''
    },
    searchClickg(){
      this.$refs.search.action = 'https://www.google.com/search'
      this.$refs.btn.name = 'q'
      this.$refs.btn.placeholder = '谷歌一下'
      this.$refs.btn.value = ''
    },
    searchClickd(){
      this.$refs.search.action = 'https://www.baidu.com/s'
      this.$refs.btn.name = 'wd'
      this.$refs.btn.placeholder = '百度一下'
      this.$refs.btn.value = ''
    },
    searchClickz(){
      this.$refs.search.action = 'https://www.zhihu.com/search'
      this.$refs.btn.name = 'q'
      this.$refs.btn.placeholder = '知乎一下'
      this.$refs.btn.value = ''
    },
    searchClickbi(){
      this.$refs.search.action = 'https://search.bilibili.com/all'
      this.$refs.btn.name = 'keyword'
      this.$refs.btn.placeholder = 'B站一下'
      this.$refs.btn.value = ''
    },
    searchClickj(){
      this.$refs.search.action = 'https://juejin.cn/search'
      this.$refs.btn.name = 'query'
      this.$refs.btn.placeholder = '掘金一下'
      this.$refs.btn.value = ''
    },

  }
}
</script>
  