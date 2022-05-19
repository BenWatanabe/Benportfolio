<template>
  <div>
    <v-row>
      <product
        v-for="(product, key) in filterdList"
        :key="key"
        :product="product"
      >
      </product
    ></v-row>
  </div>
</template>

<script>
import Product from './Product.vue';
export default {
  name: 'ProductList',
  components: { Product },
  data: () => ({
    sortYear: '全て',
    products: [
      {
        id: 1,
        name: '',
        // TODO: ここに差し替えたい画像のパスを入れてね
        image: require('@/assets/230376.jpg'),
        year: '2020',
        category: '明星大学　TOUMAIプロジェクト',
        use: 'Swift',
        urls: [
          // TODO: ここにリンクしたいURLを入れてね
          'https://www.meisei-u.ac.jp/2022/2022021401.html'
        ],
      },
      // image: "vue-portfolio/src/assets/re-vr.png",
      {
         id: 2,
         name: "情報x国際コミュニケーションxジョージア",
         image: require('@/assets/AR app-2.png'),
         year: "2021",
         category: "ARアプリケーション",
         use: "Xcode seift",
       },
      // {
      //   id: 3,
      //   name: "work3",
      //   image: "https://dummyimage.com/250x150/000/fff",
      //   year: "2018",
      //   category: "ECサイト",
      //   use: "デザイン",
      // },
      // {
      //   id: 4,
      //   name: "work4",
      //   image: "https://dummyimage.com/250x150/000/fff",
      //   year: "2019",
      //   category: "LP",
      //   use: "Vue.js",
      // },
    ],
  }),
  computed: {
    filterdList: function() {
      const newList = [];
      for (let i = 0; i < this.products.length; i++) {
        if (this.sortYear === "2020" && this.products[i].year === "2020") {
          newList.push(this.products[i]);
        } else if (
          this.sortYear === "2019" &&
          this.products[i].year === "2019"
        ) {
          newList.push(this.products[i]);
        } else if (
          this.sortYear === "2018" &&
          this.products[i].year === "2018"
        ) {
          newList.push(this.products[i]);
        } else if (this.sortYear === "全て") {
          newList.push(this.products[i]);
        }
      }
      return newList;
    },
  },
  methods: {
    sortYearChanged: function(year) {
      console.log(year);
      this.sortYear = year;
    },
  },
};
</script>
