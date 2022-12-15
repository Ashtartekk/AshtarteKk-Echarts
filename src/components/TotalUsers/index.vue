<template>
    <CommonCard title="累计用户数" value="1,087,503">
        <template>
            <div id="total-users-chart"></div>
        </template>
        <template v-slot:footer>
            <div class="total-users-footer">
                <span>日同比</span>
                <span class="emphasis">8.73%</span>
                <div class="increase"></div>
                <span>月同比</span>
                <span class="emphasis">8.73%</span>
                <div class="decrease"></div>
            </div>
        </template>
    </CommonCard>
</template>

<script>
import commonCardMixin from '../../mixins/commonCardMixin'
export default {
    name: 'TotalUsers',
    mixins: [commonCardMixin],
    mounted() {
        // 获取div的id
        const chartDom = document.getElementById('total-users-chart')
        // 完成Echarts的初始化
        const chart = this.$echarts.init(chartDom, 'light', { render: 'svg' })
        chart.setOption({
            grid: {
                top: 0,
                right: 0,
                left: 0,
                bottom: 0
            },
            xAxis: {
                type: 'value',
                show: false

            },
            yAxis: {
                type: 'category',
                show: false
            },
            series: [{
                type: 'bar',
                data: [300],
                stack: '总量',
                barWidth: 10,
                itemStyle: {
                    color: '#45c946'
                }
            }, {
                type: 'bar',
                data: [200],
                stack: '总量',
                itemStyle: {
                    color: '#ccc'
                }
            }]
        })
    }
}
</script>

<style lang="scss" scoped>
#total-users-chart {
    width: 100%;
    height: 100%
}

.total-users-footer {
    display: flex;

    .increase {
        width: 0;
        height: 0;
        border-width: 6px;
        border-color: transparent transparent red transparent;
        border-style: solid;
        margin: 0 10px 3px 5px
    }

    .decrease {
        width: 0;
        height: 0;
        border-width: 6px;
        border-color: green transparent transparent transparent;
        border-style: solid;
        margin: 5px 0 0 5px
    }
}
</style>
