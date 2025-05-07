<script>
import AppBanner from './mainComponents/AppBanner.vue';
import AppReviews from './mainComponents/AppReviews.vue';
import AppInfo from './mainComponents/AppInfo.vue';
import AppDucks from './mainComponents/AppDucks.vue';
import AppFaqs from './mainComponents/AppFaqs.vue';

export default {
  data() {
    return {
      
    };
  },
  components: {
    AppBanner,
    AppInfo,
    AppReviews,
    AppDucks,
    AppFaqs
  },
  
}
</script>

<template>
    <main>

        <AppBanner />
        <AppInfo />
        <AppReviews />
        <AppDucks />
        <AppFaqs />
       
    </main>
</template>

<style lang="scss" scoped>

    main{

        margin-top: 100px;
        font-weight: 400;
        line-height: 1.24;
        color: #3D3A38;

        
    }


</style>
