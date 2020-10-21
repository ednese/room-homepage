<template>
  <div class="top">
    <div class="top__images">
      <div class="top__buttons">
        <div v-on:click="toggleImg(true)" class="top__button_left"> <img src="../../assets/icones/icon-angle-left.svg" alt="arrow_btn" /> </div>
        <div v-on:click="toggleImg(false)" class="top__button_right"> <img src="../../assets/icones/icon-angle-right.svg" alt="arrow_btn" /> </div>
      </div>
      <img class="top__image_item one" v-bind:class="img" src="../../assets/images/image-hero-1.jpg" alt="img"/>
      <img class="top__image_item two" v-bind:class="img" src="../../assets/images/image-hero-2.jpg" alt="img"/>
      <img class="top__image_item three" v-bind:class="img" src="../../assets/images/image-hero-3.jpg" alt="img"/>
    </div>
    <div class="top__left">
      <div class="top__left_text" >
        <h1 v-for="element in elements" :key="element.name" v-bind:class="`top__left__title ${element.index} ${img}`">{{element.title}}</h1>
        <p v-for="element in elements" :key="element.name" v-bind:class="`top__left__desc ${element.index} ${img}`">{{element.desc}}</p>
        <a class="top__left__shop" href="#"><span>SHOP NOW</span><img alt="arrow" src="../../assets/icones/icon-arrow.svg"/> </a>
      </div>
    </div>
  </div>
</template>

<script>
import './top.css'

export default {
  name: 'Top',
  methods: {
    toggleImg: function (direction) {
      if ((this.img === 'first' && direction === true) || (this.img === 'last' && direction === false)) {
        this.img = 'second'
        this.shop = false
      }
      else if ((this.img === 'second' && direction === true) || (this.img === 'first' && direction === false)) {
        this.img = 'last'
        this.shop = false
      }
      else {
        this.img = 'first'
      }
    }
  },
  data () {
    const tab = [{title: 'Discover innovative ways to decorate', index:'one', desc: 'We provide unmatched quality, comfort, and style for property owners across the country. Our experts combine form andnfunction in bringing your vision to life. Create a room in your own style with our collection and make your property a reflection of you and what you love.'},
    {title: 'We are available all across the globe', index:'two', desc: "With stores all over the world, it's easy for you to find furniture for your home or place of business. Locally, we’re in most major cities throughout the country. Find the branch nearest you using our store locator. Any questions? Don't hesitate to contact us today."},
    {title: 'Manufactured with the best materials', index:'three', desc: 'Our modern furniture store provide a high level of quality. Our company has invested in advanced technology to ensure that every product is made as perfect and as consistent as possible. With three decades of experience in this industry, we understand what customers want for their home and office.'}];
    return {
      img: 'first',
      elements: tab
    }
  }
}
</script>