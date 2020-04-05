<template>
  <div>
    <h2>Webtoon</h2>
    <ul class="wrap">
      <li class="item" v-for="(item, idx) in items" :key="{idx}">
        <a :href="item.link" target="_blank">
          <img :src="item.img">
          <span class="tit">제목: {{item.name}}</span>
        </a>
        <span class="tag" v-if="item.isUpdate">N</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    items: { type: Array, default: () => [] }
  }
};
</script>

<style scoped>
h2 {
  text-align: center;
}

a {
  list-style: none;
  text-decoration: none;
}

li {
  list-style: none;
}

.wrap {
  max-width: 450px;
  width: 100%;
  margin: 0 auto;
}

.item {
  border-bottom: 1px solid #ebebeb;
  margin-bottom: 25px;
  position: relative;
}

.tit {
  display: inline-block;
  font-size: 18px;
  font-weight: bold;
  color: #000;
  padding: 20px 15px;
}

img {
  width: 150px;
  background: #ebebeb;
  border-radius: 4px;
}

.tag {
  position: absolute;
  left: 0px;
  top: 0px;
  padding: 10px 13px;
  color: #fff;
  background: #fc2332;
  font-weight: bold;
}
</style>