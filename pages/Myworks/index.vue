<template>

  <div class="container">
    <div class="portfolios">
      <div class="title_desc">
        <h2>My works</h2>
      </div>
      <ul class="v_listup">
          <li v-for="(board, idx) in listdata" :key="idx">
            <nuxt-link :to="{ name: 'Myworks', params: { id: idx }}">
                <div class="image">
                    <img :src="`${board.Image}`" alt="">
                </div>
                <div class="texts">
                    <p class="title2">{{ board.Title }}</p>
                    <h3 class="title">{{ board.From }}</h3>
                </div>
            </nuxt-link>
          </li>
      </ul>
    </div>  
  </div>
</template>

<script>
import listData from '@/static/listdata.js';

export default {
  name: 'ListPage',
  data() {
    return {
      listdata: listData,
    }
  },
  head: {
    title: 'My Works Lists',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'description'
      }
    ],
  },
}
</script>

<style scoped>
.v_listup {
  margin-top: 4rem;
}
.portfolios {
  min-height: 100vh;
}
.portfolios li {
  transition: 1s ease all;
}
.portfolios li img {
  transition: 1.5s ease all;
}
.portfolios ul li a .image {
  overflow: hidden;
}
.portfolios li:hover {
  transform: scale(1.15);
  z-index: 999;
}
.portfolios li:hover {
  box-shadow: 0 0 30px 20px rgba(0, 0, 0, 0.35);
}
.portfolios li:hover img {
  transform: translateX(-50%) translateY(-5px) scale(1.15);
  transform-origin: center top;
}
</style>