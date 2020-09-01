<template>
    <div>
        <ul>
            <li>Name: Kostya Shynkaruk</li>
            <li>Birthday: 14.11.1986</li>
            <li>Email: kos@gmail.com</li>
            <li>Address: Lviv ctiy, Ukraine</li>
        </ul>
        <div  id="map-container-google-3" class="z-depth-1-half map-container-3">
            <iframe src="https://www.google.com/maps/embed?pb=!1m14!1m12!1m3!1d2571.591950930207!2d23.951744156905793!3d49.868909221478035!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!5e0!3m2!1sru!2sua!4v1598995067254!5m2!1sru!2sua" frameborder="0" style="border:0;" allowfullscreen="" ></iframe>
        </div>
    </div>
</template>

<script>


    export default {
        name: 'Contacts',

        data () {
            return {

            }
        },

        components: {

        }
    }
</script>

<style>
    .map-container-3{
        overflow:hidden;
        padding-bottom:56.25%;
        position:relative;
        height:0;
    }
    .map-container-3 iframe{
        left:0;
        top:0;
        height:100%;
        width:100%;
        position:absolute;
    }
</style>
