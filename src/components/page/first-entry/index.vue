<template>
    <div>
        <div class="crumbs">
            <el-breadcrumb separator="/">
                <el-breadcrumb-item>
                    <i class="el-icon-lx-calendar"></i> 表单
                </el-breadcrumb-item>
                <el-breadcrumb-item>基本表单</el-breadcrumb-item>
            </el-breadcrumb>
        </div>
        <div class="container">
            <div class="page-nav mb20">
                <span>录入</span>
                <span class="fenge-span"><</span>
                <span>首次录入</span>
                <span class="fenge-span"><</span>
                <span>创建新工作薄</span>
            </div>
            <div class="page-title">创建新工作薄</div>
            <div class="form-box page-form-container">
                <el-form ref="form" :model="form" label-width="120px">
                    <el-form-item label="被试真实信息" label-width="120px">
                        <el-input v-model="form.name"></el-input>
                        <div class="tip"><span>*</span>例：光华小学二班、普陀教育学院**班级、东华师大历史系2019级本科</div>
                    </el-form-item>
                    <el-form-item label="被试公开信息">
                        <el-input v-model="form.name"></el-input>
                    </el-form-item>
                    <el-form-item label="被试年龄">
                        <el-input v-model="form.name"></el-input>
                        <div class="tip"><span>*</span>例：8~9岁、18岁以上、所有年龄</div>
                    </el-form-item>
                    <el-form-item label="提示词">
                        <el-input v-model="form.name"></el-input>
                    </el-form-item>
                    <el-form-item label="测试人数">
                        <el-input v-model="form.name"></el-input>
                        <div class="tip"><span>*</span>仅能填写数字</div>
                    </el-form-item>
                    <el-form-item label="测试时间">
                        <el-select class="w300" v-model="form.region" placeholder="请选择">
                            <el-option key="bbk" label="步步高" value="bbk"></el-option>
                            <el-option key="xtc" label="小天才" value="xtc"></el-option>
                            <el-option key="imoo" label="imoo" value="imoo"></el-option>
                        </el-select>
                        <div class="tip"><span>*</span>选择测试时长  下拉菜单内容：50秒、60秒、70秒、100秒、不限时长</div>

                    </el-form-item>

                    <el-form-item label="测试日期">
                        <el-date-picker
                                class="w300"
                                type="date"
                                placeholder="选择日期"
                                v-model="form.date1"
                                value-format="yyyy-MM-dd"
                                style="width: 100%;"
                        ></el-date-picker>
                        <div class="tip"><span>*</span>例：2015/12/28</div>

                    </el-form-item>

                    <el-form-item class="submit-content ">
                        <el-button class="sure-btn submit-btn" type="primary" @click="onSubmit">确认</el-button>
                        <el-button class="cancel-btn submit-btn">取消</el-button>
                    </el-form-item>
                </el-form>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'baseform',
    data() {
        return {
            options: [
                {
                    value: 'guangdong',
                    label: '广东省',
                    children: [
                        {
                            value: 'guangzhou',
                            label: '广州市',
                            children: [
                                {
                                    value: 'tianhe',
                                    label: '天河区'
                                },
                                {
                                    value: 'haizhu',
                                    label: '海珠区'
                                }
                            ]
                        },
                        {
                            value: 'dongguan',
                            label: '东莞市',
                            children: [
                                {
                                    value: 'changan',
                                    label: '长安镇'
                                },
                                {
                                    value: 'humen',
                                    label: '虎门镇'
                                }
                            ]
                        }
                    ]
                },
                {
                    value: 'hunan',
                    label: '湖南省',
                    children: [
                        {
                            value: 'changsha',
                            label: '长沙市',
                            children: [
                                {
                                    value: 'yuelu',
                                    label: '岳麓区'
                                }
                            ]
                        }
                    ]
                }
            ],
            form: {
                name: '',
                region: '',
                date1: '',
                date2: '',
                delivery: true,
                type: ['步步高'],
                resource: '小天才',
                desc: '',
                options: []
            }
        };
    },
    methods: {
        onSubmit() {
            this.$message.success('提交成功！');
        }
    }
};
</script>