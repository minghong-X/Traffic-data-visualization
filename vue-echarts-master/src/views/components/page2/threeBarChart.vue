<template>
    <div class="threeBarChart"></div>
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
                grid: {
                    top: "20%",
                    bottom: "15%",
                    left: 40,
                    right: 40,
                },
                tooltip: {
                    trigger: 'axis'
                },
                legend: {
                    left: "8%",
                    top: "10%",
                    itemWidth: 7,
                    itemHeight: 7,
                    textStyle: {
                        color: '#5CB1C1',
                        fontSize: 10
                    }
                },
                calculable: true,
                xAxis: [
                    {
                        type: 'category',
                        axisLine: {
                            symbol: ['none', 'arrow'],
                            symbolSize: [6, 6],
                            lineStyle: {
                                color: '#122C49'
                            }
                        },
                        axisLabel: {
                            interval: 0,
                            rotate: 40,
                            color: '#61B9C8',
                            showMaxLabel: false,
                            fontSize: 10
                        },
                        data: ["0-10min", "10-20min", "20-30min", "30-40min", "40-50min", "50-60min"]
                    }
                ],
                yAxis: [
                    {
                        type: 'value',
                        interval: 5,
                        min: 20,
                        max: 50,
                        splitNumber: 7,
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
                            fontSize: 10
                        },
                        splitLine: {
                            show: false,
                        },
                        name: '(辆)',
                        nameGap: -10,
                        nameTextStyle: {
                            color: '#61B9C8',
                            fontSize: 9,
                            align: 'right',
                            padding: [0, 6, 0, 0]
                        }
                    },
                    // {
                    //     type: 'value',
                    //     interval: 50,
                    //     position: "right",
                    //     offset: -35,
                    //     min: 0,
                    //     max: 400,
                    //     splitNumber: 7,
                    //     axisLine: {
                    //         symbol: ['none', 'arrow'],
                    //         symbolSize: [6, 6],
                    //         lineStyle: {
                    //             color: '#122C49'
                    //         }
                    //     },
                    //     axisLabel: {
                    //         color: '#61B9C8',
                    //         showMaxLabel: false,
                    //         fontSize: 10
                    //     },
                    //     splitLine: {
                    //         show: false,
                    //     },
                    //     name: '(人)',
                    //     nameGap: -10,
                    //     nameTextStyle: {
                    //         color: '#61B9C8',
                    //         fontSize: 9,
                    //         align: 'left',
                    //         padding: [0, 0, 0, 6]
                    //     }
                    // },
                    {
                        type: 'value',
                        position: "right",
                        interval: 1,
                        min: 0,
                        max: 6,
                        splitNumber: 7,
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
                            fontSize: 10
                        },
                        splitLine: {
                            show: false,
                        },
                        name: '(个)',
                        nameGap: -10,
                        nameTextStyle: {
                            color: '#61B9C8',
                            fontSize: 9,
                            align: 'left',
                            padding: [0, 0, 0, 6]
                        }
                    },
                ],
                series: [
                    {
                        name: '车流量',
                        yAxisIndex: 1,
                        type: 'bar',
                        barGap: 0,
                        barWidth: 6,
                        data: [4.5, 4.5, 3.2, 3.9, 3.8, 2.8],
                        itemStyle: {
                            barBorderRadius: [3, 3, 0, 0],
                            color: {
                                type: 'linear',
                                x: 0,
                                y: 0,
                                x2: 1,
                                y2: 0,
                                colorStops: [
                                    {
                                        offset: 0, color: 'rgba(252,145,134,1)' // 0% 处的颜色
                                    }, {
                                        offset: 1, color: 'rgba(241,88,135,1)' // 100% 处的颜色
                                    }
                                ],
                                global: false // 缺省为 false
                            } //背景渐变色
                        }
                    },
                    {
                        name: '过车数量',
                        type: 'bar',
                        barGap: 0,
                        barWidth: 6,
                        data: [45, 45, 42, 39, 38, 28],
                        itemStyle: {
                            barBorderRadius: [3, 3, 0, 0],
                            color: {
                                type: 'linear',
                                x: 0,
                                y: 0,
                                x2: 1,
                                y2: 0,
                                colorStops: [
                                    {
                                        offset: 0, color: 'rgba(144,20,238,1)' // 0% 处的颜色
                                    }, {
                                        offset: 1, color: 'rgba(74,8,211,1)' // 100% 处的颜色
                                    }
                                ],
                                global: false // 缺省为 false
                            } //背景渐变色
                        }
                    },
                    {
                        name: '车挡类型',
                        yAxisIndex: 1,
                        type: 'bar',
                        barGap: 0,
                        barWidth: 6,
                        data: [2, 4, 4, 5, 4, 3],
                        itemStyle: {
                            barBorderRadius: [3, 3, 0, 0],
                            color:  {
                                type: 'linear',
                                x: 0,
                                y: 0,
                                x2: 1,
                                y2: 0,
                                colorStops: [
                                    {
                                        offset: 0, color: 'rgba(0,204,255,1)' // 0% 处的颜色
                                    }, {
                                        offset: 1, color: 'rgba(8,59,126,1)' // 100% 处的颜色
                                    }
                                ],
                                global: false // 缺省为 false
                            } //背景渐变色
                        }
                    }
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
.threeBarChart {
    height: 100%;
    width: 100%;
}
</style>