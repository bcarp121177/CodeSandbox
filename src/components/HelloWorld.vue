<template>
  <div class="hello">
    <p>hi</p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      projectsInDb: { name: "John", age: "45", car: "ford" },
      directoryProjects: { name: "John", age: "30", car: "ford" },
     
    };
  },
  props: {
    msg: String
  },
  created() {
    this.findDups(this.projectsInDb, this.directoryProjects);
    console.log("ceated")
  },
  methods: {
    findDups(obj1, ob2) {

      var keyObj1 = Object.keys(obj1)
      var keyObj2 = Object.keys(ob2)
      var valueObj1 = Object.values(obj1)
      var valueObj2 = Object.values(ob2)
      
      var biggestKey;

      if (keyObj1.length > keyObj2.length) {
        biggestKey = keyObj1.length;
      } else {
        biggestKey = keyObj2.length;
      }

      // now compare their keys and values
      for (var i = 0; i < biggestKey; i++) {
        if (keyObj1[i] === keyObj2[i] && valueObj1[i] === valueObj2[i]) {
          console.log(valueObj2[i]);
        } else {
          // it prints keys have different values
          console.log(
            "myObj1 value: " +
              valueObj1[i] +
              "\nmyObj2 value: " +
              valueObj2[i] +
              "\n"
          );
        }
      }
    }
  }
};
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
