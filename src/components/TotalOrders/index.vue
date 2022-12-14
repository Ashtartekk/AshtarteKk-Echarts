<template>
    <CommonCard title="累计订单量" value="￥ 2,157,420">
        <template>
            <div id="total-orders-chart" style="width=50px;height=50px;"></div>
        </template>
        <template v-slot:footer>
            <span>昨日订单量</span>
            <span class="emphasis">￥ 20,000,000</span>
        </template>
    </CommonCard>
</template>

<script>
import commonCardMixin from '../../mixins/commonCardMixin'
export default {
    name: 'TotalOrders',
    mixins: [commonCardMixin],
    mounted() {
        // 获取div的id
        const chartDom = document.getElementById('total-orders-chart')
        // 完成Echarts的初始化
        const chart = this.$echarts.init(chartDom, 'light', { render: 'svg' })
        chart.setOption({
            xAxis: {},
            yAxis: {},
            series: [{
                type: 'line',
                data: [620, 432, 220, 534, 790, 430, 220, 320, 520, 340, 743, 532, 752]
            }]
        })
    }
}
</script>

<style>

</style>
