<template>
    <!-- <div class="container"> -->
    <!-- class="w-screen h-screen" -->
    <div>
        <div class="tc">
            <div class="m-auto" style="width: 400px">
                成功：
                <n-input status="success" v-model="inputValue" @change="onChange" @input="onInput"/>
            </div>
            <div class="m-auto" style="width: 400px">
                警告：
                <n-input status="warning" v-model="inputValue" @change="onChange" @input="onInput"/>
            </div>
            <div class="m-auto" style="width: 400px">
                失败：
                <n-input status="error" v-model="inputValue" @change="onChange" @input="onInput"/>
            </div>
            <div class="m-auto" style="width: 400px">
                <n-input size="xs" :disabled="newDisabled" icon="n-icon-search" iconType="before" v-model="inputValue" @change="onChange" @input="onInput"/>
                <n-input size="sm" :disabled="newDisabled" icon="n-icon-search" iconType="before" v-model="inputValue" @change="onChange" @input="onInput"/>
                <n-input size="base" :disabled="newDisabled" icon="n-icon-search" iconType="before" v-model="inputValue" @change="onChange" @input="onInput"/>
                <n-input size="lg" :disabled="newDisabled" icon="n-icon-search" iconType="before" v-model="inputValue" @change="onChange" @input="onInput"/>
                <n-input size="xl" :disabled="newDisabled" v-model="inputValue" @change="onChange" @input="onInput" clearable/>
                <p @click="clearAAA">点击清空</p>
                <n-button size="xs">测试</n-button>
                <n-radio label="1" v-model="radio"></n-radio>
                <n-radio label="2" v-model="radio"></n-radio>
                <n-radio label="3" v-model="radio"></n-radio>
                <n-radio label="4" v-model="radio"></n-radio>
                <n-radio-group v-model="test">
                    <n-radio-button label="1"></n-radio-button>
                    <n-radio-button label="2"></n-radio-button>
                    <n-radio-button label="3"></n-radio-button>
                    <n-radio-button label="4"></n-radio-button>
                </n-radio-group>
            </div>
        </div>
    </div>
</template>

<script>
    // import NCheckbox from "~/components/NCheckbox";
    // import NGrid from "~/components/NGrid";
    import NFlex from "~/components/NFlex";
    // import NContainer from "~/components/NContainer";
    // import NHeader from "~/components/NHeader";
    // import NAside from "~/components/NAside";
    // import NMain from "~/components/NMain";
    // import NFooter from "~/components/NFooter";
    import NInput from "~/components/NInput";
    import NButton from "~/components/NButton";
    import NRadio from "~/components/NRadio";
    import NRadioGroup from "~/components/NRadioGroup";
    import NRadioButton from "../components/NRadioButton";

    export default {
        components: {
            NRadioButton,
            // NCheckbox
            // NGrid
            NFlex,
            // NContainer,
            // NHeader,
            // NAside,
            // NMain,
            // NFooter
            NInput,
            NButton,
            NRadio,
            NRadioGroup
        },
        data() {
            return {
                inputValue: "",
                newDisabled: false,
                newStatus: "", //error warning success
                radio: '1',
                test: '1',
            };
        },
        mounted() {

        },
        methods: {
            clearAAA() {
                console.log(this.radio);
            },
            onChange(val) {
                console.log("获取到改变后的值:", val, this.inputValue);
            },
            onInput(val) {
                this.inputValue = val;
                console.log("传出来的值：", val, "监听到的值", this.inputValue);
                if (val == 1) {
                    this.newStatus = "success";
                } else if (val == 2) {
                    this.newStatus = "warning";
                } else if (val == 3) {
                    this.newStatus = "error";
                } else {
                    this.newStatus = "";
                }
                console.log("获取正在输入的值:", val);
            },
            clickInput(e) {
                // console.log(e);
            }
        }
    };
</script>

<style>
    /* Sample `apply` at-rules with Tailwind CSS
    .container {
      @apply min-h-screen flex justify-center items-center text-center mx-auto;
    }
    */
    .container {
        margin: 0 auto;
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
    }

    .title {
        font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
        'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
        display: block;
        font-weight: 300;
        font-size: 100px;
        color: #35495e;
        letter-spacing: 1px;
    }

    .subtitle {
        font-weight: 300;
        font-size: 42px;
        color: #526488;
        word-spacing: 5px;
        padding-bottom: 15px;
    }

    .links {
        padding-top: 15px;
    }
</style>
