<template>
  
  <header class="header">
    <div class="container">

      <nav class="header__nav">
        <div class="header__group">
          <img class="header__img" src="./src/assets/icon/mark.svg" alt="mark">
          <p class="header__text">Махачкала</p>
        </div>
        
        <div class="header__group">
          <p class="header__text">Магазины</p>

          <span class="header__subgroup">
            <p class="header__text">Покупателям</p>
            <img class="header__img header__img_arrow" src="./src/assets/icon/arrow.svg" alt="arrow">
          </span>
          
          <span class="header__subgroup">
            <p class="header__text">Юридическим лицам</p>
            <img class="header__img header__img_arrow" src="./src/assets/icon/arrow.svg" alt="arrow">
          </span>
        </div>
  
        <div class="header__group">
          <a href="tel:8-800-999-99-99">8-800-999-99-99 (c 03:00 до 22:00)</a>
        </div>
      </nav>
      
      <nav class="header__nav">
        <div class="header__group">
          <img class="logo" src="./src/assets/img/logo.jpg" alt="logo">
        </div>

        <div class="header__group header__group_input">
          <input class="header__input-search" type="text" placeholder="Быстрый поиск">
          <button class="header__btn_search">
            <img class="header__img header__img_loupe" src="./src/assets/icon/loupe.svg" alt="loupe">
          </button>
        </div>

        <div class="header__group header__group_input">
          <button class="header__btn header__btn_menu">
            <img class="header__img header__img_btn" src="./src/assets/icon/lover.svg" alt="lover">
            Избранное
            <span class="span_alert-btn">3</span>
          </button>

          <button class="header__btn header__btn_menu">
            <img class="header__img header__img_btn" src="./src/assets/icon/balance.svg" alt="balance">
            Сравнить
          </button>

          <button class="header__btn header__btn_menu">
            <img class="header__img header__img_btn" src="./src/assets/icon/cart.svg" alt="cart">
            Корзина
            <span class="span_alert-btn">7</span>
          </button>
        </div>
      </nav>

      <nav class="header__nav">
        <div class="header__group">
          <button class="header__btn header__btn_catalog">
            <img class="header__img header__img_btn header__img_catalog" src="./src/assets/icon/burger.svg" alt="burger">
            Каталог
          </button>
        </div>

        <div class="header__group header__group_btn">
          <button class="header__btn header__btn_category">
            <img class="header__img header__img_btn header__img_category" src="./src/assets/icon/agenda.svg" alt="agenda">
            Бумажная продукция
          </button>

          <button class="header__btn header__btn_category">
            <img class="header__img header__img_btn header__img_category" src="./src/assets/icon/briefcase.svg" alt="briefcase">
            Товары для школы
          </button>

          <button class="header__btn header__btn_category">
            <img class="header__img header__img_btn header__img_category" src="./src/assets/icon/stationery.svg" alt="stationery">
            Товары для творчества
          </button>

          <button class="header__btn header__btn_category">
            <img class="header__img header__img_btn header__img_category" src="./src/assets/icon/abacus.svg" alt="abacus">
            Товары для торговли
          </button>

          <button class="header__btn header__btn_category header__btn_action">
            <img class="header__img header__img_btn header__img_category" src="./src/assets/icon/tag.svg" alt="tag">
            Скидки и акции
          </button>
        </div>
      </nav>

    </div>
  </header>

</template>

<script>
export default {
  name: 'App',

  data: () => ({

  }),

  watch: {

  },

  methods: {

  },

  computed: {

  },

  components: {

  },

  created() {

  },

  mounted() {

  },
}
</script>

<style>

</style>
