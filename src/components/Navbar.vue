<template>
    <div id="nav">
         <b-navbar toggleable="lg" id="nav-body" type="dark" variant="info">
            <b-navbar-brand href="#" id="app-title"><span style="font-size: 30px">S</span>tand App</b-navbar-brand>
            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

            <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav>
                <b-nav-item href="#"><router-link to="/">Home</router-link></b-nav-item>
            </b-navbar-nav>
             <b-navbar-nav>
                <b-nav-item href="#"><router-link to="team-board">Teem</router-link></b-nav-item>
            </b-navbar-nav>

            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">
                <b-nav-item-dropdown text="Lang" right>
                <b-dropdown-item href="#">EN</b-dropdown-item>
                <b-dropdown-item href="#">HE</b-dropdown-item>
                </b-nav-item-dropdown>
            </b-navbar-nav>
            </b-collapse>
        </b-navbar>
         
        
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
#app-title{
    color : white;
    margin-top: -10px;
}

#nav a {
  color: white;
}

#nav a.router-link-exact-active {
  font-weight: bold;
}
</style>