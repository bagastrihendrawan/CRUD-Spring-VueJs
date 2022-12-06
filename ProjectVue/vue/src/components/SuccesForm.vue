<template>
    <div>
        <center>
            <div>
            <div class="border p-2">
            <div class="card-body border-color-pink">
            <h5 class="card-title">Success!</h5>
            <p class="card-text" >Your Data Has Been {{apdet}}</p>
            <router-link to="/home" class="btn btn-primary">Back</router-link>
            </div>
        </div>
    </div>
        </center>

    </div>
    
</template>

<script>

export default {
    name: 'ProjectVueSuccesForm',

    props: ['apdet'],

};
</script>

<style  scoped>

</style>