<template>
    <ElDialog title="" :visible.sync="centerDialogVisible" width="30%" center >
        <span>Are you sure you want to delete the item {{}}'?</span>
        <span slot="footer" class="dialog-footer">
            <el-button @click="centerDialogVisible = false">Cancel</el-button>
            <el-button type="primary" @click="centerDialogVisible = false">Confirm</el-button>
        </span>
    </ElDialog>
</template>

<script>
export default {
    name: "Confirm", 
    data: () => ({
        centerDialogVisible: false
    }),
}
</script>