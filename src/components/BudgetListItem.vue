<template>
    <div class="list-item">
        <i :class="icon"></i>
        <span class="budget-comment"> {{ item.comment }} </span>
        <span class="budget-value" :class="color"> {{ item.value }} </span>
        <ElButton type="danger" size="mini" @click="deleteItem(item.id)">Delete</ElButton>.
    </div>
</template>

<script>
export default {
    name: "BudgetListItem",
    props: {
        item: {
            type: Object,
        },
        changeStyle: {
            type: Function,
        }
    },
    methods: {
        deleteItem(id) {
            this.$emit("deleteItem", id);
        }
    },
    computed: {
        color:  {
           get(){
               return this.changeStyle(this.item.value);
           }
       },
       icon: {
           get() {
               if (this.item.type === "OUTCOME"){
                   return 'el-icon-bottom';
               }
               return 'el-icon-top';
            }
        }
    },
}
</script>

<style scoped>
.list-item {
    display: flex;
    align-items: center;
    padding: 10px;
}
.budget-value {
    font-weight: bold;
    margin-left: auto;
    margin-right: 20px;
}
</style>