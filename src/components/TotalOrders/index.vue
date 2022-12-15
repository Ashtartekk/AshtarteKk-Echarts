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
            xAxis: {
                type: 'category',
                show: false,
                boundaryGap: false
            },
            yAxis: { show: false },
            series: [{
                type: 'line',
                data: [620, 432, 220, 534, 790, 430, 743, 532, 752],
                areaStyle: {
                    color: 'purple'
                },
                lineStyle: {
                    width: 0
                },
                itemStyle: {
                    opacity: 0
                },
                smooth: true
            }],
            grid: {
                top: 0,
                bottom: 0,
                left: 0,
                right: 0
            }
        })
    }
}
</script>

<style scoped>
#total-orders-chart {
    width: 100%;
    height: 100%;
}
</style>
