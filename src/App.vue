<template>
  <div>
    <div class ="nav">
      <ul>
        <li  v-for="navi in navies" :key="navi.id">
          <a @click="selectNavi(navi.id)" href="#">{{ navi.title }}</a>
        </li>
      </ul>
    </div>
    <div class="result">
      <span>You choose : {{ selectedNavi.title }}</span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navies: [
        { id: 1,  title: 'Services' },
        { id: 2,  title: 'Products' },
        { id: 3,  title: 'About' },
        { id: 4,  title: 'Gallery' },
        { id: 5,  title: 'Login' },
      ],
      selectedNavi: '',
    }
  },
  methods: {
    selectNavi(id) {
      this.selectedNavi = this.navies.filter(navi => navi.id === id)[0]
    }
  }
}
</script>

<style>
  * {
    padding: 0;
    margin: 0;
  }

  body {
    text-align: center;
    font-family: 'Verdana';
    margin:10px 10px;
  }

  .nav {
    background-color: rgb(44, 84, 100);
    min-width: 100px;
    color:white;
    padding:0 10px;
  }

  .nav > ul {
    margin: auto;
    width:50%;
  }

  .nav > ul li {
    display: inline;
    margin-right: 20px;
  }

  .nav > ul li > a {
    color:white;
  }

  .nav > ul li > a:hover {
    text-decoration: none;
    color:yellow;
  }

  .result {
    background-color: rgb(163, 163, 224);
    color:rgb(78, 31, 47);
  }

  .result > span {
    font-weight:bold;
  }

</style>
