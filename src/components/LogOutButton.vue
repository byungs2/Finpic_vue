<template>
    <div id = "logOutButton" v-if="token != null && token.length != 0" >
        <button type = "button" v-on:click = "LogOutLink">Log Out</button>
    </div>
</template>

<script>
const storage = window.sessionStorage;

export default {
    name : "LogInButton",
    methods : {
        LogOutLink : function(){
            storage.setItem("jwt-auth-token", "");
            storage.setItem("userNumber", "");
            this.$router.push("/mainpage");
            this.$router.go("/");
        }
    },
    data : function(){
        return {
            token : storage.getItem("jwt-auth-token")
        }
    },
}
</script>