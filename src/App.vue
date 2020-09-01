<template>
    <div id="wrapper">
        <h1>Vue Lesson Three</h1>
        <ul class="nav nav-pills">
            <router-link
                tag="li"
                to="/"
                class="nav-link"
        >Home
        </router-link>
            <router-link
                    tag="li"
                    to="/contacts"
                    class="nav-link"
            >Contacts
            </router-link>
            <router-link
                    tag="li"
                    to="/my-projects"
                    class="nav-link"
            >My Projects
            </router-link>
        </ul>
        <router-view/>
    </div>
</template>

<script>

export default {
  name: 'App',

  data () {
      return {

      }
  },

}
</script>

<style>
    #wrapper {
        margin: 0 40px;
    }
    li {
        margin-bottom: 15px;
    }

</style>
