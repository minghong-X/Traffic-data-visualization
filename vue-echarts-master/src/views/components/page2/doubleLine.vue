<template>
    <div class="doubleLine"></div>
</template>

<script>
export default {
    name: '',
    data() {
        return {}
    },
    methods: {
        setChart() {
            let option = {
                tooltip: {
                    trigger: 'axis'
                },
                legend: {
                    left: "11%",
                    top: "10%",
                    itemWidth: 7,
                    itemHeight: 7,
                    textStyle: {
                        color: '#5CB1C1',
                        fontSize: 10
                    }
                },
                grid: {
                    top: '12%',
                    left: '10%',
                    right: '10%',
                    bottom: '10%',
                    containLabel: false
                },

                xAxis: {
                    type: 'category',
                    boundaryGap: false,
                    axisLine: {
                        symbol: ['none', 'arrow'],
                        symbolSize: [6, 6],
                        symbolOffset: [0, 10],
                        lineStyle: {
                            color: '#122C49'
                        }
                    },
                    axisTick: {show: false},
                    axisLabel: {
                        interval: 0,
                        color: '#61B9C8',
                        fontSize: 9
                    },
                    data: ["0-10min", "10-20min", "20-30min", "30-40min", "40-50min", "50-60min"]
                },
                yAxis: [
                    {
                        type: 'value',
                        scale: true,
                        max: 500,
                        min: 300,
                        interval: 30,
                        axisLine: {
                            symbol: ['none', 'arrow'],
                            symbolSize: [6, 6],
                            lineStyle: {
                                color: '#122C49'
                            }
                        },
                        axisLabel: {
                            color: '#61B9C8',
                            showMaxLabel: false,
                            fontSize: 9
                        },
                        name: '(辆)',
                        nameGap: -10,
                        nameTextStyle: {
                            color: '#61B9C8',
                            fontSize: 9,
                            align: 'right',
                            padding: [0, 6, 0, 0]
                        },
                        splitLine: {
                            show: false,
                        },
                    },
                    {
                        type: 'value',
                        scale: true,
                        max: 20,
                        min: 10,
                        axisLine: {
                            symbol: ['none', 'arrow'],
                            symbolSize: [6, 6],
                            lineStyle: {
                                color: '#122C49'
                            }
                        },
                        axisLabel: {
                            color: '#61B9C8',
                            showMaxLabel: false,
                            fontSize: 9
                        },
                        name: '(个)',
                        nameGap: -10,
                        nameTextStyle: {
                            color: '#61B9C8',
                            fontSize: 9,
                            align: 'left',
                            padding: [0, 0, 0, 6]
                        },
                        interval: 2,
                        splitLine: {
                            show: false,
                        },
                    }
                ],
                series: [
                    {
                        name: '过车数量',
                        type: 'line',
                        smooth: true,
                        symbol: 'none',
                        lineStyle: {
                            color: '#F39800',
                        },
                        itemStyle: {
                            color: '#F39800'
                        },
                        data: [365, 438, 370, 370, 349, 327]
                    },
                    {
                        name: '过车类型',
                        yAxisIndex: 1,
                        type: 'line',
                        smooth: true,
                        symbol: 'none',
                        lineStyle: {
                            color: '#BF232A',

                        },
                        itemStyle: {
                            color: '#BF232A'
                        },
                        data: [12, 16, 14, 14, 12, 11]
                    },
                ]
            };
            let myChart = this.$echarts(this.$el);

            myChart.clear();
            myChart.resize()
            myChart.setOption(option);
        }
    },
    mounted() {
        this.setChart()
    },
}
</script>

<style lang="less" scoped>
.doubleLine {
    height: 100%;
    width: 100%;
}
</style>