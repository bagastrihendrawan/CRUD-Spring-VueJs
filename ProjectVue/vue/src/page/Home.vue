<template>
    <div>     
        <Header></Header>
        <Add></Add>
        <CardComp></CardComp>
        <Copyrightt></Copyrightt>
    </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Add from '@/components/Add.vue';
import CardComp from '@/components/CardComp.vue';
import Copyrightt from '@/components/Copyrightt.vue';
export default {
    name: 'VueDetail',
    components: {
        Header,
        Add,
        CardComp,
        Copyrightt
    }

};
</script>

<style lang="scss" scoped>

</style>