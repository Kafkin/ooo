<template>
  
  <header class="header">
    <div class="container">

      <nav class="header__nav">
        <div class="header__group">
          <img class="header__img" src="@/assets/icon/mark.svg" alt="mark">
          <p class="header__text">Махачкала</p>
        </div>
        
        <div class="header__group">
          <p class="header__text">Магазины</p>

          <span class="header__subgroup">
            <p class="header__text">Покупателям</p>
            <img class="header__img header__img_arrow" src="@/assets/icon/arrow.svg" alt="arrow">
          </span>
          
          <span class="header__subgroup">
            <p class="header__text">Юридическим лицам</p>
            <img class="header__img header__img_arrow" src="@/assets/icon/arrow.svg" alt="arrow">
          </span>
        </div>
  
        <div class="header__group">
          <a href="tel:8-800-999-99-99">8-800-999-99-99 (c 03:00 до 22:00)</a>
        </div>
      </nav>
      
      <nav class="header__nav">
        <div class="header__group">
          <img class="logo" src="@/assets/img/logo.jpg" alt="logo">
        </div>

        <div class="header__group header__group_input">
          <input class="header__input-search" type="text" placeholder="Быстрый поиск">
          <button class="header__btn_search">
            <img class="header__img header__img_loupe" src="@/assets/icon/loupe.svg" alt="loupe">
          </button>
        </div>

        <div class="header__group header__group_input">
          <button class="header__btn header__btn_menu">
            <img class="header__img header__img_btn" src="@/assets/icon/lover.svg" alt="lover">
            Избранное
            <span class="span_alert-btn">3</span>
          </button>

          <button class="header__btn header__btn_menu">
            <img class="header__img header__img_btn" src="@/assets/icon/balance.svg" alt="balance">
            Сравнить
          </button>

          <button class="header__btn header__btn_menu">
            <img class="header__img header__img_btn" src="@/assets/icon/cart.svg" alt="cart">
            Корзина
            <span class="span_alert-btn">7</span>
          </button>
        </div>
      </nav>

      <nav class="header__nav">
        <div class="header__group">
          <button class="header__btn header__btn_catalog">
            <img class="header__img header__img_btn header__img_catalog" src="@/assets/icon/burger.svg" alt="burger">
            Каталог
          </button>
        </div>

        <div class="header__group header__group_btn">
          <button class="header__btn header__btn_category">
            <img class="header__img header__img_btn header__img_category" src="@/assets/icon/agenda.svg" alt="agenda">
            Бумажная продукция
          </button>

          <button class="header__btn header__btn_category">
            <img class="header__img header__img_btn header__img_category" src="@/assets/icon/briefcase.svg" alt="briefcase">
            Товары для школы
          </button>

          <button class="header__btn header__btn_category">
            <img class="header__img header__img_btn header__img_category" src="@/assets/icon/stationery.svg" alt="stationery">
            Товары для творчества
          </button>

          <button class="header__btn header__btn_category">
            <img class="header__img header__img_btn header__img_category" src="@/assets/icon/abacus.svg" alt="abacus">
            Товары для торговли
          </button>

          <button class="header__btn header__btn_category header__btn_action">
            <img class="header__img header__img_btn header__img_category" src="@/assets/icon/tag.svg" alt="tag">
            Скидки и акции
          </button>
        </div>
      </nav>

    </div>
  </header>


  
  <main class="main">
    <div class="container">
      
      <section class="section section_banner">
        <v-carousel :items="arrItems"></v-carousel>
      </section>

      <section class="section section_stock-products">
        <h1 class="section__title">Акции</h1>

        <span class="span span_group">
          <a class="section__link" href="#">Все акции</a>
          <img src="./assets/icon/small_arrow_right.svg" alt="small_arrow_right">
        </span>
        
        <div class="container container_products">
          <v-product 
            v-for="( product, index ) in stockProducts" :key="index"
            :product="product"
          ></v-product>
        </div>
      </section>

    </div>
  </main>

</template>

<script>
import vCarousel from "@/components/Carousel/vCarousel.vue"
import vProduct from "@/components/vProduct.vue"

export default {
  name: 'App',

  data: () => ({

    arrItems: [
      'Banner.jpg', 'Banner.jpg', 'Banner.jpg',
      'Banner.jpg', 'Banner.jpg', 'Banner.jpg',
      'Banner.jpg', 'Banner.jpg', 'Banner.jpg',
      'Banner.jpg', 'Banner.jpg', 'Banner.jpg',
      'Banner.jpg'
    ],

    stockProducts: [
      { 
        description: 'Клей-карандаш Berlingo “Ultra”,21г', 
        img: 'glue.jpg', 
        discount: 15, 
        price: 58.20, 
        mark: false,
        stars: 4
      },

      { 
        description: 'Печать самонаборная автоматическая Colop, Ø40мм, 2 круга', 
        img: 'seal.jpg', 
        discount: 25, 
        price: 780.45, 
        mark: true,
        stars: 3 
      },

      { 
        description: 'Ранец Berlingo Expert "Hockey league" 37*28*16см, 2 отделения, 1 карман, анатомическая спинка', 
        img: 'knapsack.png', 
        discount: 10, 
        price: 2920.50, 
        mark: true,
        stars: 1
      },

      { 
        description: 'Диспенсер настольный Berlingo для канцелярской клейкой ленты, ассорти', 
        img: 'scotch.png', 
        discount: 10, 
        price: 475.38, 
        mark: false,
        stars: 5
      },
    ]

  }),

  watch: {

  },

  methods: {

  },

  computed: {

  },

  components: {
    vCarousel, vProduct
  },

  created() {

  },

  mounted() {

  },
}
</script>

<style>
  @import url( '@/styles/css/config.min.css' );
</style>
