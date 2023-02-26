<template>
  
  <article class="product">
    <p class="product__discount">-{{ product.discount }}%</p>

    <img class="product__img" :src="require( `@/assets/img/${ product.img }` )" alt="clay">

    <div class="product__group-stars">
      <svg 
        width="14" height="13" viewBox="0 0 14 13" fill="none" xmlns="http://www.w3.org/2000/svg"
        :style="{ '--color-star': colorStar( index ) }"
        v-for="( el, index ) in 5" :key="index" 
        class="product__star"  
      >
        <path d="M7 0L9.163 4.27865L14 4.96898L10.5 8.29758L11.326 13L7 10.7787L2.674 13L3.5 8.29758L0 4.96898L4.837 4.27865L7 0Z" fill="#47A31C"/>
      </svg>


      <svg :class="['product__mark', { 'product__mark_active': product.mark }]" width="18" height="16" viewBox="0 0 18 16" fill="none" xmlns="http://www.w3.org/2000/svg">
        <g clip-path="url(#clip0_1_142)">
          <path d="M2.17671 2.52944C1.3258 3.3681 0.821793 4.48568 0.758125 5.6758L0.758124 5.67581C0.694957 6.85711 0.998723 7.88201 1.72294 8.98088C2.052 9.48028 2.63312 10.1095 3.27178 10.7305C3.91423 11.3553 4.62871 11.985 5.23611 12.4875C5.85876 13.0027 6.5849 13.5714 7.25132 14.0126C7.5843 14.233 7.90742 14.425 8.19867 14.5628C8.48282 14.6972 8.76491 14.7939 9.007 14.7939C9.25139 14.7939 9.53489 14.6978 9.82054 14.5634C10.1129 14.4259 10.4363 14.2343 10.769 14.0142C11.4348 13.5738 12.1579 13.0062 12.7772 12.492C13.38 11.9916 14.0899 11.3632 14.7297 10.7379C15.3658 10.1161 15.9459 9.48477 16.2776 8.98032L16.0688 8.84295L16.2776 8.98032C16.7619 8.24396 17.323 7.18531 17.2421 5.6758C17.1785 4.48568 16.6745 3.36811 15.8236 2.52945C14.9594 1.67759 13.8278 1.20605 12.6378 1.20605C10.9005 1.20605 9.66795 2.49385 9.01776 3.20164C8.3933 2.49737 7.1534 1.20605 5.36242 1.20605C4.17249 1.20605 3.0409 1.67758 2.17671 2.52944ZM2.17671 2.52944L2.3522 2.70749L2.17671 2.52944Z" fill="none" stroke="#1D1D1B" stroke-width="1.5"/>
        </g>
        <defs>
        <clipPath id="clip0_1_142">
        <rect width="18" height="16" fill="white"/>
        </clipPath>
        </defs>
      </svg>
    </div>

    <p class="product__description">
      {{ product.description }}
    </p>

    <span class="product__group-price">
      <p class="product__price">{{ priceСorrection( discountPrice ) }} ₽</p>
      <p class="product__subtracted-price">{{ priceСorrection( product.price ) }} ₽</p>
    </span>

    <div class="product__group-btn">
      <button class="product__btn product__btn_dim">Сравнить</button>
      <button class="product__btn product__btn_bright">В корзину</button>
    </div>
  </article>

</template>

<script>
export default {

  name: 'vProduct',

  props: {
    product: {
      required: true,
      type: Object
    }
  },

  methods: {
    priceСorrection( float ) {
      return float.toString().split('.').join(',')
    },

    colorStar( index ) {
      return index < this.product.stars 
        ? ( this.product.stars > 3 ? '#47A31C' : ( this.product.stars > 1 ? '#F2C111' : '#E0001B' ) )
        : '#F5F5F5'
    }
  },  

  computed: {
    discountPrice() {
      return (this.product.price - ( this.product.price / 100 * this.product.discount )).toFixed( 2 ).split('.').join(',')
    },

    
  }

}
</script>