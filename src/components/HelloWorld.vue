<template>
  <div class="hello">
    <el-row>
      <el-col :span="24">
        <div class="grid-content bg-purple-dark">
          <el-button @click="addCookie">设置cookie</el-button>
          <el-button
            type="primary"
            @click="deleteCookie"
          >删除cookie</el-button>
        </div>
      </el-col>
    </el-row>
    <el-row>
      <el-col :span="24">
        {{cookieValue}}
      </el-col>
    </el-row>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      cookieValue: ''
    }
  },
  methods: {
    addCookie() {
      this.$Cookies.set('person', { 'name': 'user', 'age': '18' });
      this.cookieValue = this.$Cookies.get('person');
    },
    deleteCookie() {
      this.$Cookies.remove('person');
      this.cookieValue = ''
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
