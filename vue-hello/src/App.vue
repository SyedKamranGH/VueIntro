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

  <h3 v-bind:style="{
    color:highlightColor
  }" >Inline Style</h3>
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
      highlightColor: 'orange'
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
