<template>
  <div class="hello">
    <hr>
    <h1>{{ msg_value.message }}</h1>
  </div>
  <hr>
</template>

<script>
var axios = require('axios');
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  data() {
    return {
      msg_value: {data:'helloo'}
    }
  },
  created() {
    var config = {
      method: 'get',
      url: 'https://cnxelection.com/test',
      headers: { }
    };

    axios(config)
    .then(response => {
      this.msg_value = response.data
    })
    .catch(function (error) {
      console.log(error);
    });


  }
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
