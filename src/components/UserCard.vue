<template>
    <div class="card" @click="$emit('onClick', user)">
        <img class="card__image" :src="UserImage" />
        <div class="card__text-info">
            <div class="card__name title">{{ user?.name }}</div>
            <div class="card__email text">{{ user?.email }}</div>
        </div>
    </div>
</template>

<script>
import UserImage from "@/assets/user-image.png"
export default {
    name: "UserCard",
    props: {
        user: {
            type: Object,
            required: true
        },
    },
    data() {
        return {
            UserImage
        }
    }
}
</script>

<style lang="scss" scoped>
@import "@/components/UserCard/style.scss";
</style>
