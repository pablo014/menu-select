<template>
    <div class="menu-item">
        <div class="item-details">
            <h3 class="item-name">{{ item.title }}</h3>
            <p class="item-description">{{ item.description }}</p>
            <ul class="item-ingredients">
                <li v-for="ingredient in ingredients" :key="ingredient">{{ ingredient }}</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "MenuItem",
    props: {
        item: {
            type: Object,
            required: true,
        }
    },
    data(props) {
        const ingredients = JSON.parse(props.item.ingredients);
        return {
            ingredients,
        }
    },
}
</script>

<style scoped>
.menu-item {
    @apply border-4 rounded-3xl border-amber-400 p-5;
    display: flex;
    align-items: center;
    margin-bottom: 20px;
}


.item-details {
    flex: 1;
}

.item-name {
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 5px;
}

.item-description {
    font-size: 16px;
    color: #777;
    margin-bottom: 10px;
}

.item-ingredients {
    list-style-type: disc;
    margin-left: 20px;
}

.item-ingredients li {
    margin-bottom: 5px;
}
</style>