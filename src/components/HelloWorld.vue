<template>
  <div class="hello">
    <button @click="test">Test</button>

{{info}}
{{what}}

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: function() {
    return {
      info: '',
      what: "what is going on",
    }
  },
  methods: {
    test: function() {
      console.log('test')
          this.$axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(response => {

        console.log(response);
         this.info = response;
        })
    }
  } // end of methods
} // end of default
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
