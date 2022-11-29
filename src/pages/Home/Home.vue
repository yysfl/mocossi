<template>
    <Header></Header>
    <div class="pg-sect sect1">
        <div class="sect-title">Story & Gameplay</div>
        <div class="lay-row tabs-group">
            <div class="tab-item" :class="[tabIndex == index ? 'active' : '']" v-for="(item, index) in tabList"
                :key="index" @click="handleTabChange(index)">{{ item.name }}
            </div>
        </div>
        <div class="tab-cont">
            <div class="img-wrap">
                <img src="../../assets/images/banner1.jpg" class="fit-img" alt="" v-if="tabIndex == 0">
                <img src="../../assets/images/banner2.jpg" class="fit-img" alt="" v-else-if="tabIndex == 1">
                <img src="../../assets/images/banner3.jpg" class="fit-img" alt="" v-else-if="tabIndex == 2">
                <div class="img-text">
                    <p>2038 was a landmark year in technology and production that brought humanity to an unprecedented
                        level of development. Skyscrapers rose, unmanned vehicles filled the streets, factories in
                        industrial zones worked nonstop and cities never slept. Over time, this progress led to a
                        variety of alarming consequences: depletion of natural resources, inability of plants and
                        animals to survive, and increased pollution.</p>

                    <p>Ten years later, advancements in science and technology enabled mankind to expand the search for
                        interstellar planets in the universe. The search uncovered an Earth-like planet that is home to
                        several intelligent alien species. Discovered by astronomer X! (Mr-X-clamation), planet Mocossi
                        has potential resources to improve and revitalize the environment on Earth.</p>
                </div>
            </div>
        </div>
    </div>
    <div class="pg-sect sect2">
        <div class="sect-title">Testimonials</div>
        <div class="slider-wrap">
            <div class="slider-box">
                <div class="swiper">
                    <div class="swiper-wrapper">
                        <div class="swiper-slide" v-for="(item, index) in 9" :key="index">
                            <div class="slider-item">
                                <div class="item-cont">
                                    <p>I had to pick these @officialmocossi! Excited to be part of them fam and the
                                        future of this
                                        project. </p>
                                </div>
                                <div class="lay-row item-footer">
                                    <div class="avatar">
                                        <img src="https://mocossi.com/static/media/2.f1131df5f69c03e475c9.jpg"
                                            class="fit-img" alt="">
                                    </div>
                                    <div>
                                        <div class="u-name">@ChenoskiPR</div>
                                        <div class="u-name">Twitter</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="lay-row slider-btn">
                <div class="btn-item prev" @click="handleSliderBtn('prev')"></div>
                <div class="btn-item next" @click="handleSliderBtn('next')"></div>
            </div>
        </div>
    </div>
</template>
<script setup>
// This starter template is using Vue<script setup> SFCs
import { ref, reactive, onMounted } from 'vue';
import Header from '../../components/Header/Header.vue';
import Swiper from 'swiper';
const tabList = reactive([
    { name: 'Story' },
    { name: 'Breeding' },
    { name: 'Mocossi Planet' },
]);
const tabIndex = ref(0);
const handleTabChange = (index) => {
    if (tabIndex.value == index) return;
    tabIndex.value = index;
};
const slider = ref({});
const initSlider = () => {
    slider.value = new Swiper('.swiper', {
        slidesPerView: 3,
        spaceBetween: 30,
    });
};
const sliderIndex = ref(0);
const handleSliderBtn = (action) => {
    if (action == 'prev') {
        sliderIndex.value = sliderIndex.value <= 0 ? 0 : sliderIndex.value - 1;
    } else if (action == 'next') {
        sliderIndex.value = sliderIndex.value >= 2 ? 2 : sliderIndex.value + 1;
    }
    slider.value.slideTo(sliderIndex.value);
};
onMounted(() => {
    initSlider();
});
</script>
<style scoped>
.pg-sect {
  background: center no-repeat #350028;
  background-size: cover;
}
.pg-sect .sect-title {
  font-size: 32px;
  line-height: 66px;
  color: #fff;
  font-family: iCiel Cadena;
  padding: 40px 0;
  text-align: center;
  text-shadow: -3px -3px 0 #c0346a, -3px -2px 0 #c0346a, -3px -1px 0 #c0346a, -3px 0 0 #c0346a, -3px 1px 0 #c0346a, -3px 2px 0 #c0346a, -3px 3px 0 #c0346a, -2px -3px 0 #c0346a, -2px -2px 0 #c0346a, -2px -1px 0 #c0346a, -2px 0 0 #c0346a, -2px 1px 0 #c0346a, -2px 2px 0 #c0346a, -2px 3px 0 #c0346a, -1px -3px 0 #c0346a, -1px -2px 0 #c0346a, -1px -1px 0 #c0346a, -1px 0 0 #c0346a, -1px 1px 0 #c0346a, -1px 2px 0 #c0346a, -1px 3px 0 #c0346a, 0 -3px 0 #c0346a, 0 -2px 0 #c0346a, 0 -1px 0 #c0346a, 0 0 0 #c0346a, 0 1px 0 #c0346a, 0 2px 0 #c0346a, 0 3px 0 #c0346a, 1px -3px 0 #c0346a, 1px -2px 0 #c0346a, 1px -1px 0 #c0346a, 1px 0 0 #c0346a, 1px 1px 0 #c0346a, 1px 2px 0 #c0346a, 1px 3px 0 #c0346a, 2px -3px 0 #c0346a, 2px -2px 0 #c0346a, 2px -1px 0 #c0346a, 2px 0 0 #c0346a, 2px 1px 0 #c0346a, 2px 2px 0 #c0346a, 2px 3px 0 #c0346a, 3px -3px 0 #c0346a, 3px -2px 0 #c0346a, 3px -1px 0 #c0346a, 3px 0 0 #c0346a, 3px 1px 0 #c0346a, 3px 2px 0 #c0346a, 3px 3px 0 #c0346a;
}
.pg-sect.sect1 {
  padding-bottom: 30px;
  background-image: url(../../assets/images/banner-bg1.jpg);
}
.pg-sect.sect2 {
  height: 600px;
  background-image: url(../../assets/images/banner-bg2.jpg);
}
.pg-sect .tabs-group {
  margin-bottom: 30px;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
}
.pg-sect .tabs-group .tab-item {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
  margin-right: 20px;
  padding-bottom: 5px;
  background: url(../../assets/images/tab-bg1.svg) center no-repeat;
  background-size: 100% 100%;
  height: 65px;
  width: 178px;
  color: #fff;
  cursor: pointer;
  font-family: iCiel Cadena;
}
.pg-sect .tabs-group .tab-item:last-of-type {
  margin-right: 0;
}
.pg-sect .tabs-group .tab-item.active {
  background-image: url(../../assets/images/tab-bg2.svg);
}
.pg-sect .tab-cont .img-wrap {
  width: 780px;
  height: 440px;
  margin: 0 auto;
  position: relative;
  border-radius: 20px;
  overflow: hidden;
}
.pg-sect .tab-cont .img-wrap .img-text {
  position: absolute;
  left: 12px;
  right: 12px;
  bottom: 12px;
  z-index: 3;
  padding: 15px;
  height: 100px;
  background: rgba(53,0,40,0.9);
  border-radius: 16px;
  overflow: auto;
  font-size: 14px;
  color: #fff;
}
.pg-sect .slider-wrap {
  padding-bottom: 40px;
}
.pg-sect .slider-wrap .slider-box {
  width: 80%;
  max-width: 1200px;
  margin: 0 auto 30px;
}
.pg-sect .slider-wrap .slider-box .slider-item {
  width: 100%;
  background: url(../../assets/images/block-bg.svg) center no-repeat;
  background-size: 100% 100%;
  position: relative;
}
.pg-sect .slider-wrap .slider-box .slider-item .item-cont {
  padding: 20% 30px 0;
  height: 300px;
  font-size: 14px;
  color: #fff;
}
.pg-sect .slider-wrap .slider-box .slider-item .item-footer {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 30px;
  padding: 15px;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  color: #fff;
}
.pg-sect .slider-wrap .slider-box .slider-item .item-footer .avatar {
  width: 40px;
  height: 40px;
  background: #fff;
  margin-right: 10px;
  border-radius: 50%;
  overflow: hidden;
}
.pg-sect .slider-wrap .slider-box .slider-item .item-footer .u-name {
  font-size: 14px;
}
.pg-sect .slider-wrap .slider-box .slider-item .item-footer .u-desp {
  font-size: 12px;
}
.pg-sect .slider-wrap .slider-btn {
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
}
.pg-sect .slider-wrap .slider-btn .btn-item {
  width: 32px;
  height: 32px;
  margin-right: 20px;
  background: no-repeat center #460042;
  background-size: 50% 50%;
  border-radius: 50%;
  cursor: pointer;
  border: 1px solid #26002a;
}
.pg-sect .slider-wrap .slider-btn .btn-item:last-child {
  margin-right: 0;
}
.pg-sect .slider-wrap .slider-btn .btn-item:hover {
  background-color: #d3006d;
}
.pg-sect .slider-wrap .slider-btn .btn-item.prev {
  background-image: url(../../assets/images/icon-arrow-left@64.png);
}
.pg-sect .slider-wrap .slider-btn .btn-item.next {
  background-image: url(../../assets/images/icon-arrow-right@64.png);
}

</style>
