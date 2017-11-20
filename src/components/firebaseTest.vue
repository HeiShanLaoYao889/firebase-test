<template>
  <div id="firebaseTest">
      <h1>这是测试firebase的页面</h1>
      <form action="">
          <label for="name">用户名：</label>
          <input type="text" id="name" v-model="mesg.name">
          <br><br>
          <label for="name">年龄：</label>
          <input type="text" id="age" v-model="mesg.age">
          <br><br>
          <label for="name">性别：</label>
          <input type="text" id="sex" v-model="mesg.sex">
          <br><br>       
      </form>
      <br><br><br>
      <button @click="addJson">添加数据</button>
      <button @click="getJson">获取数据</button>
  </div>
</template>
<script>
export default {
  name:"firebaseTest",
  data(){
      return {
          mesg:{
              id:"",
              name:"",
              age:null,
              sex:""
          }
      }
  },
  methods:{
      addJson(){
          let url = 'https://blogdemo-4b71b.firebaseio.com/post.json',
              data={
                  id:this.mesg.id,
                  name:this.mesg.name,
                  age:Number(this.mesg.age),
                  sex:this.mesg.sex
              };
        this.$http.post(url,data).then((response) => {
            console.log(response);
            if(response.statusText == 'OK'){
                alert('添加成功');
            }
        });
      },
      getJson(){
          this.$http.get('https://blogdemo-4b71b.firebaseio.com/post.json').then(function (response) {
              let newArray = [];
              for (const key in response.body) {
                  response.body[key].id = key;
                  newArray.push(response.body[key]);
              }
              console.log(newArray);
          })
      }
  }

}
</script>
<style>

</style>
