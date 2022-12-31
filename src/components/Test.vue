<template>
  <div>
    <h2>テストコンポーネント</h2>
    <p>{{ message }}</p>
    <p>{{ message.length * 10 }}</p>
    <p v-text="message"></p>
    <p>
      <button v-on:click="count++">You clicked me {{ count }} times.</button>
    </p>
    <p><span v-if="seen">Now you see me</span></p>
    <div id="list-rendering">
      <ol>
        <li v-for="todo in todos">
          {{ todo.text }}
        </li>
      </ol>
    </div>
    <p>{{ datetime }}</p>
    <p>{{ add }}</p>
    <p>{{ x }}</p>
  </div>
</template>

<script>
export default {
  name: "Test", //このコンポーネントの名前
  data() {
    return {
      count: 0,
      seen: true,
      todos: [
        { text: "Learn JavaScript" },
        { text: "Learn Vue" },
        { text: "Build something awesome" },
      ],
    };
  },
  props: {
    message: String,
    todo: [],
    x: {
      type: String,
      default: "デフォルト",
      required: true, //xが必須かどうかtrueは必須
      validator: (value) => {
        return ["バッグ", "トートバッグ", "バックパック"].indexOf(value) !== -1;
      },
    },
  },
  computed: {
    datetime: function () {
      return new Date();
    },
    add: function () {
      return 1 + this.x;
    },
  },
};
</script>

<style scoped>
h2 {
  margin: 40px 0 0;
  color: aqua;
}
</style>