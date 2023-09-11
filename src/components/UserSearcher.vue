<template>
    <div class="searcher">
        <div class="searcher__title title">Поиск сотрудников</div>
        <custom-input :placeholder="'Введите Id или имя'" v-model="searchValue"></custom-input>
        <div class="searcher__results title">Результаты</div>
        <div v-if="!filteredUsers.length" class="text">Ничего не найдено</div>
        <div class="searcher__cards">
            <user-card v-for="user in filteredUsers" :key="user.id" :user="user" @onClick="setUser"></user-card>
        </div>
    </div>
</template>

<script>
import CustomInput from "@/components/UI/CustomInput/CustomInput.vue";
import UserCard from "@/components/UserCard/UserCard.vue";

export default {
    name: "UserSearcher",
    components: {UserCard, CustomInput},
    data() {
        return {
            searchValue: "",
        }
    },
    computed: {
        filteredUsers() {
            if (!this.searchValue) {
                return []
            }
            return this.$store.state.users.filter(el => {
                const string = `${el.name} ${el.id}`.toLowerCase()
                return string.includes(this.searchValue.toLowerCase());
            })
        },
    },
    methods: {
        setUser(user) {
            this.$store.dispatch('setUser', {user})
        }
    }
}
</script>

<style lang="scss" scoped>
@import "@/components/UserSearcher/style.scss";
</style>
