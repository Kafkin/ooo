<template>

  <div class="carousel">
    <div class="carousel__container-items">
      
      <v-carousel-item 
        v-for="( item, index ) in items" :key="`item-${ index }`"
        :current="currentItem" 
        :dir="direction" 
        :index="index"
        :item="item" 
      >
      </v-carousel-item>
      
    </div>

    <div class="carousel__container-btn">
      <img @click="prev" class="carousel__arrow" src="@/assets/icon/arrow_left.svg" alt="arrow_left">
      <img @click="next" class="carousel__arrow" src="@/assets/icon/arrow_right.svg" alt="arrow_right">
    </div>

    <div class="carousel__container-dots">
      <span 
        :class="['carousel__dot', { 'carousel__dot_active': currentItem === index }]"
        v-for="( dot, index ) in items" :key="`dot-${ index }`"
      >
      </span>
    </div>
  </div>

</template>

<script>
import vCarouselItem from './vCarouselItem.vue';

export default {
  name: 'vCarousel',

  props: {
    items: {
      required: true,
      type: Array
    }
  },

  data: () => ({
    direction: 'slide-out',
    disabled: false,
    currentItem: 0

  }),

  methods: {

    next() {
      if( this.disabled ) return
      this.direction = 'slide-out'

      this.currentItem < this.items.length - 1 
        ? this.currentItem += 1
        : this.currentItem = 0

      this.disabledBtn()
    },

    prev() {
      if( this.disabled ) return
      this.direction = 'slide-in'

      this.currentItem > 0
        ? this.currentItem -= 1
        : this.currentItem = this.items.length - 1 

      this.disabledBtn()
    },

    disabledBtn() {
      this.disabled = true

      setTimeout(() => {
        this.disabled = false
      }, 700)
    }
    
  },

  components: { 
    vCarouselItem
  },
  
}
</script>