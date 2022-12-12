<template>
    <div class="pieChart"></div>
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
                title: [
                    {
                        text: "【K31】",
                        left: '12%',
                        bottom: '12%',
                        textStyle: {
                            color: "#fff",
                            fontSize: 12
                        }
                    },
                    {
                        text: "【K32】",
                        left: '46%',
                        bottom: '12%',
                        textStyle: {
                            color: "#fff",
                            fontSize: 12
                        }
                    },
                    {
                        text: "【K33】",
                        right: '12%',
                        bottom: '12%',
                        textStyle: {
                            color: "#fff",
                            fontSize: 12
                        }
                    }
                ],
                tooltip: {
                    trigger: 'item',
                    // formatter: "{a} <br/>{b} : {c} ({d}%)"
                    formatter: "{a} <br/>{b} : {c} "
                },
                legend: {
                    data: [
                        {name: '0-10min', icon: 'circle'},
                        {name: '10-20min', icon: 'circle'},
                        {name: '20-30min', icon: 'circle'},
                        {name: '30-40min', icon: 'circle'},
                        {name: '40-50min', icon: 'circle'},
                        {name: '50-60min', icon: 'circle'},
                    ],
                    left: "8%",
                    top: "10%",
                    itemWidth: 7,
                    itemHeight: 7,
                    textStyle: {
                        color: '#00CCFF',
                        fontSize: 10
                    }
                },
                series: [
                    {
                        name: '【K31】',
                        type: 'pie',
                        radius: '40%',
                        center: ['17%', '50%'],
                        data: [
                            {value: 1312, name: '0-10min'},
                            {value: 1143, name: '10-20min'},
                            {value: 1158, name: '20-30min'},
                            {value: 1155, name: '30-40min'},
                            {value: 1093, name: '40-50min'},
                            {value: 1047, name: '50-60min'},
                        ],
                        // label: {
                        //     fontSize: 8,
                        //     color: '#00CCFF'
                        // },
                        // labelLine: {
                        //     length: 15,
                        //     length2: 10,
                        //     lineStyle: {
                        //         color: '#3F3F5C'
                        //     }
                        // },
                        label: {
                            show: false,
                        },
                        labelLine: {
                            show: false,
                        },
                        itemStyle: {
                            color: function (params) {
                                var colorList = ['#F74F64', '#00CCFF', '#315371', '#142AFE', '#9814FE', '#F39800'];
                                return colorList[params.dataIndex];
                            },
                            emphasis: {
                                shadowBlur: 10,
                                shadowOffsetX: 0,
                                shadowColor: 'rgba(0, 0, 0, 0.5)'
                            }
                        }
                    },
                    {
                        name: '【K32】',
                        type: 'pie',
                        radius: '40%',
                        center: ['50%', '50%'],
                        data: [
                            {value: 273, name: '0-10min'},
                            {value: 239, name: '10-20min'},
                            {value: 223, name: '20-30min'},
                            {value: 240, name: '30-40min'},
                            {value: 266, name: '40-50min'},
                            {value: 236, name: '50-60min'},
                        ],
                        // label: {
                        //     fontSize: 8,
                        //     color: '#00CCFF'
                        // },
                        // labelLine: {
                        //     length: 15,
                        //     length2: 10,
                        //     lineStyle: {
                        //         color: '#3F3F5C'
                        //     }
                        // },
                        label: {
                          show: false,
                        },
                        labelLine: {
                          show: false,
                        },
                        itemStyle: {
                            color: function (params) {
                                var colorList = ['#F74F64', '#00CCFF', '#315371', '#142AFE', '#9814FE', '#F39800'];
                                return colorList[params.dataIndex];
                            },
                            emphasis: {
                                shadowBlur: 10,
                                shadowOffsetX: 0,
                                shadowColor: 'rgba(0, 0, 0, 0.5)'
                            }
                        }
                    },
                    {
                        name: '【K33】',
                        type: 'pie',
                        radius: '40%',
                        center: ['82%', '50%'],
                        data: [
                            {value: 2445, name: '0-10min'},
                            {value: 2117, name: '10-20min'},
                            {value: 2083, name: '20-30min'},
                            {value: 2135, name: '30-40min'},
                            {value: 2119, name: '40-50min'},
                            {value: 1993, name: '50-60min'},
                        ],
                        // label: {
                        //     fontSize: 8,
                        //     color: '#00CCFF'
                        // },
                        // labelLine: {
                        //     length: 15,
                        //     length2: 10,
                        //     lineStyle: {
                        //         color: '#3F3F5C'
                        //     }
                        // },
                        label: {
                          show: false,
                        },
                        labelLine: {
                          show: false,
                        },
                        itemStyle: {
                            color: function (params) {
                                var colorList = ['#F74F64', '#00CCFF', '#315371', '#142AFE', '#9814FE', '#F39800'];
                                return colorList[params.dataIndex];
                            },
                            emphasis: {
                                shadowBlur: 10,
                                shadowOffsetX: 0,
                                shadowColor: 'rgba(0, 0, 0, 0.5)'
                            }
                        }
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
.pieChart {
    height: 100%;
    width: 100%;
    padding: 0 20px;
}
</style>