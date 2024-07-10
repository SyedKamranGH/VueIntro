<template>
  <h1>{{ greet }} World of Vue js, {{ name }}</h1>
  <div v-html="channel"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Boolean Bind</button>
  <h2 class="underline">Underline text</h2>
  <h2 class="underline" v-bind:class="status">Status</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">
    sold out insideOut movie ?
  </h2>
  <h2 v-bind:class="['new', 'promoted']">Newly promoted movies</h2>
  <h2 v-bind:class="[isSoldOut ? 'sold-out' : 'new', isPromoted && 'promoted']">
    Array conditional movies
  </h2>
  <h2
    v-bind:class="{
      promoted: isPromoted,
      new: !isSoldOut,
      'sold-out': isSoldOut,
    }"
  >
    Object conditional movie
  </h2>

  <h3
    v-bind:style="{
      color: highlightColor,
    }"
  >
    Inline Style
  </h3>

  <template v-if="display">
    <h4
      :style="{
        color: highlightColor,
      }"
      v-if="num === 0"
    >
      The number is zero
    </h4>
    <h4 v-else-if="num > 0">The number is greater then zero</h4>
    <h4 v-else-if="num < 0">The number is less then zero</h4>
    <h4 v-else>Not a Number</h4>
  </template>

  <h1 v-show="display" >Display Using v-show</h1>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      greet: "Hello",
      name: "Kami",
      channel: "<b>ESS</b>",
      headingId: "heading",
      isDisabled: false,
      status: "danger",
      isPromoted: true,
      isSoldOut: false,
      highlightColor: "orange",
      num: 0,
      display: true,
    };
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
  color: olivedrab;
}

.sold-out {
  color: red;
}
</style>
