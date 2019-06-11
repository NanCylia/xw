<template>
  <div>
    <div class="table">用户管理</div>
    <table class="my-table">
      <thead>
      <tr>
        <th>序号</th>
        <th>姓名</th>
        <th>性别</th>
        <th>年龄</th>
        <th>毕业学校</th>
        <th>操作</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="(user,index) in users">
        <td>{{ index+1 }}</td>
        <td>{{ user.name }}</td>
        <td>{{ user.gender }}</td>
        <td>{{ user.age }}</td>
        <td>{{ user.school }}</td>
        <td><button @click="remove">删除</button></td>
      </tr>
      <tr>
        <td></td>
        <td><input type="text" id="name" v-model="user.name"></td>
        <td><input type="text" id="gender" v-model="user.gender"></td>
        <td><input type="text" id="age" v-model="user.age"></td>
        <td><input type="text" id="school" v-model="user.school"></td>
        <td><button @click="submit">提交</button></td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default {
      data(){
          return{
              user:['name','gender','age','school'],
              users:[
                  {'name':'曹小武','gender':'男','age':'23','school':'新疆职业大学'}
              ]
          }
      },
      methods:{
        submit:function(){
            this.users.push(this.user)
        },
          remove:function(index){
              this.users.splice(index,1)
          }
      }
  }
</script>

<style>
  .my-table{
    margin: 0 auto;
  }
  .my-table table {
    width:100%;
    margin:15px 0
  }
  .my-table th {
    background-color:blue;
    color:white;
  }
  .my-table,.my-table th,.my-table td
  {
    font-size:0.95em;
    text-align:center;
    padding:4px;
    border:1px solid black;
    border-collapse:collapse
  }
  .table{
    font-size: 30px;
  }
</style>
