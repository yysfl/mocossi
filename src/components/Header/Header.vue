<template>
    <header class="lay-row pg-header">
        <div class="left">
            <div class="logo">
                <img src="../../assets/images/hd-logo.png" class="auto-img" alt="">
            </div>
        </div>  
        <div class="center">
            <div class="lay-row menu-list">
                <div class="menu-item" :class="[index == menuIndex? 'active': '']" v-for="(item,index) in menuList" :key="index" @click="handleMenuChange(index)">{{item.name}}</div>
            </div>
        </div>  
        <div class="lay-row right">
            <div class="notice">
                <img src="../../assets/images/notification-icon.svg" alt="" class="auto-img">
            </div>
            <div class="btn">Connect Wallet</div>
        </div>
    </header>
</template>
<script setup>
    import {reactive, ref} from 'vue';
    const menuIndex = ref(0);
    const menuList = reactive([
        {name: 'Home'},{name: 'Whitepaper'},{name: 'News'},{name: 'Encyclopedia'},{name: 'Breeding'},{name: 'Land'},{name: 'Airdrop'},{name: 'Marketplace'},
    ]);
    const handleMenuChange = (index) => {
        if(menuIndex.value == index) return;
        menuIndex.value = index;
    };
</script>
<style scoped>
.pg-header {
  height: 56px;
  padding: 0 20px;
  background: #3c2336;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  line-height: normal;
}
.pg-header >.left .logo {
  width: 114px;
}
.pg-header > .center {
  -webkit-box-flex: 1;
      -ms-flex: 1;
          flex: 1;
  height: 100%;
}
.pg-header > .center .menu-list {
  height: 100%;
}
.pg-header > .center .menu-list .menu-item {
  padding: 0 10px;
  margin: 0 20px;
  height: 100%;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  font-size: 16px;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  position: relative;
  cursor: pointer;
  color: #fff;
  font-family: iCiel Cadena;
  font-weight: 900;
}
.pg-header > .center .menu-list .menu-item:hover,
.pg-header > .center .menu-list .menu-item.active {
  text-shadow: 2px 0 0 #dc1c98, -2px 0 0 #dc1c98, 0 2px 0 #dc1c98, 0 -2px 0 #dc1c98, 1px 1px #dc1c98, -1px -1px 0 #dc1c98, 1px -1px 0 #dc1c98, -1px 1px 0 #dc1c98, 0 0 20px #dc1c98;
}
.pg-header > .center .menu-list .menu-item.active:before {
  content: '';
  background: url(../../assets/images/menu-border-top.png) center no-repeat;
  height: 8px;
  background-size: 100% 100%;
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
}
.pg-header > .center .menu-list .menu-item.active:after {
  content: '';
  background: url(../../assets/images/menu-border-bottom.png) center no-repeat;
  height: 8px;
  background-size: 100% 100%;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
}
.pg-header > .right {
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
}
.pg-header > .right .notice {
  width: 36px;
  height: 36px;
  margin-right: 20px;
}
.pg-header > .right .btn {
  height: 30px;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  border-radius: 8px;
  color: #fff;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  font-family: iCiel Cadena;
  font-size: 12px;
  cursor: pointer;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
  overflow: hidden;
  padding: 0 10px;
  -o-text-overflow: ellipsis;
     text-overflow: ellipsis;
  background: #f65f70;
  border: 1px solid #ba2673;
  text-shadow: -2px -2px 0 #ba2673, -2px -1px 0 #ba2673, -2px 0 0 #ba2673, -2px 1px 0 #ba2673, -2px 2px 0 #ba2673, -1px -2px 0 #ba2673, -1px -1px 0 #ba2673, -1px 0 0 #ba2673, -1px 1px 0 #ba2673, -1px 2px 0 #ba2673, 0 -2px 0 #ba2673, 0 -1px 0 #ba2673, 0 0 0 #ba2673, 0 1px 0 #ba2673, 0 2px 0 #ba2673, 1px -2px 0 #ba2673, 1px -1px 0 #ba2673, 1px 0 0 #ba2673, 1px 1px 0 #ba2673, 1px 2px 0 #ba2673, 2px -2px 0 #ba2673, 2px -1px 0 #ba2673, 2px 0 0 #ba2673, 2px 1px 0 #ba2673, 2px 2px 0 #ba2673;
}
</style>
