<template>
  <div class="psy-list">
    <div class="list" v-for="li in data" :key="li.index">
      <div class="cover-box">
        <image class="cover" mode="aspectFill" :src="li.cover" v-if="li.state" />
        <image class="cover cover-none" mode="aspectFill" :src="li.cover" v-else />
      </div>
      <text class="psy-name" v-if="li.state">{{li.name}}</text>
      <text class="psy-name name-none" v-else>{{li.name}}</text>
      <text class="psy-look" v-if="li.state">查看更多 &gt;</text>
      <text class="psy-look" v-else>即将上线</text>
    </div>
  </div>
</template>

<script>
export default {
  props: ['data']
}
</script>

<style scoped>
.psy-list {
  align-items: center;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: flex-start;
  margin-top: 20px;
  width: 750px;
  background-color: #fff;
}
.list {
  align-items: center;
  padding: 20px 0;
  width: 250px;
  border-width: 1px;
  border-style: solid;
  border-color: #eee;
  text-align: center;
}
.cover-box {
  margin: 0 auto;
  width: 150px;
  height: 150px;
  border-width: 2px;
  border-style: solid;
  border-color: #eee;
  border-radius: 200px;
}
.cover {
  margin: 5px;
  width: 136px;
  height: 136px;
  border-radius: 200px;
}
.cover-none {
  opacity: .4;
}
.psy-name {
  display: block;
  margin: 4px;
  font-size: 30px;
}
.name-none {
  color: #999;
}
.psy-look {
  display: block;
  color: #999;
  font-size: 22px;
}
</style>
