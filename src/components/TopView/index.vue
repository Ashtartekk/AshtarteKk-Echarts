<template>
    <div>
        <el-row :gutter="20">
            <el-col :span="6">
                <el-card shadow="hover">
                    <TotalSales />
                </el-card>
            </el-col>
            <el-col :span="6">
                <el-card shadow="hover">
                    <TotalOrders />
                </el-card>
            </el-col>
            <el-col :span="6">
                <el-card shadow="hover">
                    <TodayUser />
                </el-card>
            </el-col>
            <el-col :span="6">
                <el-card shadow="hover">
                    <TotalUsers />
                </el-card>
            </el-col>
        </el-row>
    </div>
</template>

<script>
import TotalSales from '../TotalSales'
import TotalOrders from '../TotalOrders'
import TodayUser from '../TodayUser'
import TotalUsers from '../TotalUsers'
export default {
    name: 'TopView',
    components: { TotalSales, TotalOrders, TodayUser, TotalUsers }
}
</script>

<style>

</style>
