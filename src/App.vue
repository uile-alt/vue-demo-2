<template>
  <div id="app">
    {{ text }}
    <br />
    {{ text.split(",").reverse().join(",") }}<br />
    计算属性:
    {{ reverseText }}<br />
    我的名字是：{{ fullName }}
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      text: "123,456,789",
      firstName: "wu",
      lastName: "yanzu",
    };
  },
  computed: {
    fullName: {
      get: function () {
        return this.firstName + this.lastName;
      },
      set: function (newValue) {
        console.log("get被调用");
        let names = newValue.split(",");
        this.firstName = names[0];
        this.lastName = names[1];
      },
    },
    reverseText: function () {
      return this.text.split(",").reverse().join(",");
    },
  },
  methods: {},
  mounted: function () {
    this.fullName = "zhang,fei";
  },
};
</script>

<style>
</style>
