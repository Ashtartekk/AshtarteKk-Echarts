<template>
    <CommonCard title="今日交易用户数" value="81,014">
        <template>
            <div id="today-users-chart"></div>
        </template>
        <template v-slot:footer>
            <span>退货率 </span>
            <span class="emphasis">5.14%</span>
        </template>
    </CommonCard>
</template>

<script>
import commonCardMixin from '../../mixins/commonCardMixin'
export default {
    name: 'TodayUser',
    mixins: [commonCardMixin],
    mounted() {
        // 获取div的id
        const chartDom = document.getElementById('today-users-chart')
        // 完成Echarts的初始化
        const chart = this.$echarts.init(chartDom)
        chart.setOption({
            series: [
                {
                    type: 'bar',
                    data: [401, 425, 123, 421, 435, 523, 215, 234, 323, 123, 976, 436, 322, 234],
                    barWidth: '60%'
                }
            ],
            xAxis: {
                type: 'category',
                data: ['00:00', '01:00', '02:00', '03:00', '04:00', '05:00', '06:00', '07:00', '08:00', '09:00', '10:00', '11:00', '12:00', '13:00'],
                show: false
            },
            yAxis: { show: false },
            grid: {
                top: 0,
                left: 0,
                bottom: 0,
                right: 0
            }
        })
    }
}
</script>

<style scoped>
#today-users-chart {
    width: 100%;
    height: 100%
}
</style>
