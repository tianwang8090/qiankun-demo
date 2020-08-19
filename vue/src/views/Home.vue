<template>
  <div class="home">

    <el-button @click="handleClick">点这里， 看控制台打印</el-button>

    <p>
      event instanceof MouseEvent:     <b>{{value}}</b>
    </p>
    <p>expected to be 'true'</p>

  </div>

</template>

<script>
  export default {
    name: 'home',
    data() {
      return {
        event: null
      };
    },
    computed: {
      value () {
        return this.event instanceof MouseEvent;
      }
    },
    methods: {
      handleClick (e) {
        this.event = e;
        console.log(e);
        console.log(MouseEvent);
        console.log(e instanceof MouseEvent); // MouseEvent ，qiankun 开启默认开启了sandbox之后，这里输出 false, 关闭 sandbox后，输出 true
      }
    },
  };
</script>
