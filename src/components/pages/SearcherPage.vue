<template>
    <div class="container">
        <user-searcher></user-searcher>
        <user-view></user-view>
    </div>
</template>

<script>
import {mapState} from "vuex";
import UserImage from "@/assets/user-image.png"
import UserSearcher from "@/components/UserSearcher.vue";
import UserView from "@/components/UserView.vue";

export default {
    name: "SearcherPage",
    components: {UserView, UserSearcher},

}
</script>

<style lang="scss" scoped>
.container {
    display: flex;
    justify-content: space-between;
    height: 80vh;
    border-radius: 10px;
    background: #FDFDFD;
    box-shadow: 0 0 10px 0 rgba(0, 0, 0, 0.10);
    overflow: hidden;
}
</style>
