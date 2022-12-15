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
                data: [450],
                stack: '总量',
                barWidth: 10,
                itemStyle: {
                    color: '#45c946'
                }
            }, {
                type: 'bar',
                data: [250],
                stack: '总量',
                itemStyle: {
                    color: '#ccc'
                }
            },
            {
                type: 'custom',
                data: [390],
                stack: '总量1',
                renderItem: (params, api) => {
                    const value = api.value(0)
                    const endPoint = api.coord([value, 0])
                    return { type: 'path', position: endPoint, shape: { d: 'M0 767.909l512.029-511.913L1024 767.909 0 767.909z', x: 20, y: 2, width: 10, height: 10 }, style: { fill: '#45c946' } }
                }
            },
            {
                type: 'custom',
                data: [390],
                stack: '总量1',
                renderItem: (params, api) => {
                    const value = api.value(0)
                    const endPoint = api.coord([value, 0])
                    return { type: 'path', position: endPoint, shape: { d: 'M1024 255.996 511.971 767.909 0 255.996 1024 255.996z', x: 20, y: -12, width: 10, height: 10 }, style: { fill: '#45c946' } }
                }
            }
            ]
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

<svg t="1671115177967" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="1356" width="200" height="200"><path d="" fill="#272636" p-id="1357"></path></svg>
<svg t="1671115512181" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="1496" width="200" height="200"><path d="" fill="#272636" p-id="1497"></path></svg>
