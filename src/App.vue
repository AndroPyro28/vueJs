<template>

  <div>{{ `${greet} ${name}` }}</div>

  <div v-html="channel"></div>

  <div v-html="hack"></div> <!-- binding html attribute with text -->

  <h2 :id="headingId">Heading</h2>  <!-- binding data into attributes-->
  
  <button :disabled="isDisabled" v-on:click="(e) => toggleDisabled(true, e)"> <!-- onClick function with methods-->
    disabled button
  </button>
  <!-- short term @click="method"-->
  <h3 v-bind:class="status">h3</h3>
  <h2 v-bind:class='isPromoted && "promoted"'>Promoted Movie</h2>
  <h2 v-bind:class="isSoldOut ? `sold-out` : `new` ">Movie</h2> <!-- conditional binding classes  -->

  <h2 :class="['new', 'promoted']" > newly promoted movie </h2>
  <h2 :class="[isPromoted && 'promoted', !isSoldOut ? `soldOut` : `new`]" > Array conditional movie </h2> <!-- array -->


  <h2 :class="{
    promoted: isPromoted,
    new: !isSoldOut,
    soldOut: !isSoldOut
  }" >object conditional movie
  </h2>


  <h2 :style="{
    color: highlightColor,
    fontSize: `${headerSize}px`,
  }" >Inline style</h2>

  <h2 :style="headerStyleObject" >Inline style</h2>

  <div :style="[baseStyleObject, successStyleObject]" > Success </div>
  <div :style="[baseStyleObject, dangerStyleObject]" > Danger </div>

</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "andro",
      greet: "hello",
      channel: "<b>Codevolution</b>",
      hack: `<button href='#' onclick="alert('you have been hacked')"> Win a prize </button>`,
      headingId: "heading",
      isDisabled: false,
      status: "underline",
      isPromoted: false,
      isSoldOut: false,
      highlightColor: 'orange',
      headerSize: 50,
      headerStyleObject: {
        color: 'orange',
        fontSize: `50px`,
      },
      baseStyleObject: {
        fontSize: '50px',
        padding: '10px',
        textAlign:'start'
      },
      successStyleObject: {
        color:'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
        padding:'50px',
        textAlign:'center'
      },
      dangerStyleObject: {
        color:'darkred',
        backgroundColor:'red',
        border:'1px solid darkred',
        padding:'50px',
        textAlign:'center'
      }
    };
  },
  methods: {
    toggleDisabled(bool, e) {
      this.isDisabled = bool;
      console.log(e.target.innerText);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}
.new {
  color: green;
}
.soldOut {
  color: red;
  text-decoration: line-through ;
}
</style>
