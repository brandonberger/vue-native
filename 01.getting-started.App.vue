<template>
    <view class="container">
        <button v-bind:title="message" v-bind:on-press="handleBtnPress"/>
    </view>
    <view class="text-container">
        <text>Payem</text>
    </view>
</template>
<script>
    export default {
        data: function() {
            return {
                message: "Hello World - Vue Native"
            };
        },
        methods: {
            handleBtnPress: function() {
                alert('Btn Press');
            }
        }
    };
</script>
<style>

.text-container {
    flex: 1;
    margin-bottom: 30;
}

.container {
  flex: 1;
  background-color: white;
  align-items: center;
  justify-content: center;
}
.text-color-primary {
  color: blue;
  font-size: 30;
}

.text-container {
    color:blue;
    font-size:30px;
}
</style>
