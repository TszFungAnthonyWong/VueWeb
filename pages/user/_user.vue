<template>
<div>
    <h1>{{firstName+"  "+lastName}}</h1>
    <p>user id: {{id}}</p>
</div>
</template>

<script>
export default {
data(){
        return{
            firstName : null,
            lastName : null,
            id : null
        }
    },

created(){
    let user = this.$route.params.user;
    user = user?user.split('-'):'';
    this.firstName = user[0]?user[0].charAt(0).toUpperCase() + user[0].slice(1):'';
    this.lastName = user[1]?user[1].charAt(0).toUpperCase() + user[1].slice(1):'';
    this.id = user[2];
},

validate ({ params }) {
    return /^\w*-\w*-\d+$/.test(params.user)
  },


head() {    
    return{
        title: this.firstName + " " + this.lastName,
        meta:[
           {name:this.firstName+this.lastName, content: this.id} 
        ]
    }
}
};
</script>