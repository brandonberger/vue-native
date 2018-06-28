<!-- Additional Notes for personal use -->
<!-- --------------------------------- -->
<!-- List running android emulators: $ `adb devices -l` -->
<!-- Kill running emulator $ `adb -s emulator-5554 emu kill` -->

<template>
	<!-- View is a container, designed to be nested inside other views and can have 0 to many children of any type -->
	<view>
		<!-- Native Component for displaying text
			Text supports nesting, styling, and touch handling -->
		<text class="message">{{ message }}</text>
		<!-- v-bind is called a directive -->
		<!-- Directives are prefixed with v- -->
		<!-- To inticate they are special attributes provided by Vue Native -->
		<!-- Which internally bind with React Native -->
		<!-- Here it is basically saying "keep this elements `title` attrtibute
				up-to-date with the `message` property on the Vue Instance" -->
		<button v-bind:title="message" v-bind:on-press="handleBtnPress" />

		<!-- Native component for displaying images, including 
		network images, static resources, temp local images, and images from local disk, such as cammera roll
		-->
		<!-- <image :source="{require('/vue-native/img/favicon.png')}" /> -->
		<!-- <image :style="{width: 50, height: 50}"
			   :source="{uri: 'https://facebook.github.io/react-native/docs/assets/favicon.png'}"
		/> -->
		<!-- <image :style="{width: 66, height: 58}"
			   :source="{uri: 'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADMAAAAzCAYAAAA6oTAqAAAAEXRFWHRTb2Z0d2FyZQBwbmdjcnVzaEB1SfMAAABQSURBVGje7dSxCQBACARB+2/ab8BEeQNhFi6WSYzYLYudDQYGBgYGBgYGBgYGBgYGBgZmcvDqYGBgmhivGQYGBgYGBgYGBgYGBgYGBgbmQw+P/eMrC5UTVAAAAABJRU5ErkJggg=='}"
		/> -->
	<!-- </view> -->
<!-- </template> -->
<!-- <template> -->
	<!-- Textinput -->
	<!-- Foundational component for inputting text into the app via a keyboard.
	Props provide configurability for serveral features, such as auto-correction, auto-capitalization, 
	placeholder text, and different keyboard types, such as a numeric keypad
	 -->
		<text-input
        :style="{height: 40, borderColor: 'gray', borderWidth: 1}"
        v-model="text" />

	    <!-- Button -->
	    <!-- A basic button component -->
	    <button
	    	:on-press="onPressLearnMore"
	    	title="Learn More"
	    	color="#841584"
	    	accessibility-label="Learn More about this purple button"
    	/>
    	<!-- End Button -->


    	<!-- FlatList -->
    	<!-- An interface for rending simple, flat lists, supporting the following features: -->
	    	<!-- Fully cross-platform -->
	    	<!-- Optional Horizontal Mode -->
	    	<!-- Configurable viewability callbacks -->
	    	<!-- Header Support -->
	    	<!-- Footer Support -->
	    	<!-- Separator Support -->
	    	<!-- Pull to Refresh -->
	    	<!-- Scroll loading -->
	    	<!-- .ScrolltoIndex support -->
    	<!-- One of the drawbacks using FlatList is the renderItem method should return JSX
    		 with the actual React Native components. Fix Coming Soon-->
    	<flat-list
        :data="{[{key: 'a'}, {key: 'b'}]}"
        :render-item="{({item}) => renderList(item)"
    	/>
    	<!-- End FlatList -->


    	<!-- Alert -->
    	<!-- Launches an alert dialog with the specified title and message -->
    	<!-- Optionally provides a list of buttons. Tapping any button with fire the respective
    	onPress callback and dmsmiss the alert. By default, the only button will be an 'Ok' button -->
<!-- 
    	<button
    		:on-press="onPressLearnMore"
    		title="Learn More"
    		color="#841584"
    		accessbility-label="Learn more about this purple button"
    	/> -->

    	<!-- End alert -->

    	<!-- StatusBar -->
    	<!-- <status-bar
    		background-color="blue"
    		bar-style="light-content"
    	/>
	 -->    
 	<!-- End StatusBar -->
	<!-- </view> -->
	<!-- Switch -->
	<!-- Renders a boolean input. -->
	<!-- This is a controlled component that requires an on-value-change callback that updates the value prop in order for teh component to reflect user actions. -->
	<!-- <view style={styles.container}>
		<switch
			:on-value-change="handleChange"
			:value="value"
		/> -->
	<!-- End Switch -->

    </view>
	<!-- ActivityIndicator -->
	<!-- Displays a circular loading indicator -->
	<!-- <view :style="{flex: 1, justify-content: 'center'}">
		<activity-indicator size="large" color="#0000ff" />
	</view> -->
	<!-- ScrollView -->
	<!-- Component that wraps platform ScrollView while providing intergration with
		touch locking "responder" system -->
		<!-- <scroll-view :content-container-style="{contentContainer: {
			padding-vertical: 20
		}}"> -->
			<!-- Content goes here -->
		<!-- </scroll-view> -->
</template>
<script>
	// JS //
	export default {


	// Switch
	// 	data: function() {
	// 		return {
	// 			value: false
	// 		}
	// 	},
	// 	methods: {
	// 		handleChange: () => {
	// 			this.value = !this.value
	// 		}
	// 	}
	// End Switch


	// Alert
	// import { Alert } from 'react-native';
	// 	methods: {
	// 		onPressLearnMore: function() {
	// 			Alert.alert(
	// 				'Alert Title',
	// 				'My Alert Msg',
	// 				[
	// 					{text: 'Ask me later', onPress: () => console.log('Ask me later pressed')},
	// 					{text: 'Cancel', onPress: () console.log('Cancel Pressed'), style: 'cancel'},
	// 					{text: 'OK', onPress: () => console.log('Ok Pressed')},
	// 				],
	// 				{cancelable: false}
	// 			);
	// 		}
	// 	}
	// End Alert



	// Button
		// methods: {
		// 	onPressLearnMore: function() {
		// 		alert('Hello')
		// 	}
		// }
	// End Button

	// FlatList
	// 	methods: {
	// 		renderList: (item) => {
	// 			return (<Text>{item}<Text>)
	// 		}
	// 	}
	// End FlatList

		data: function() {
			return {
				message: "Hello World"
			};
		},
		methods: {
			handleBtnPress: function() {
				alert('Btn Press');
			},
			onPressLearnMore: function() {
				alert('Hello')
			},
			renderList: (item) => {
				return (<Text>{item}<Text>)
			}
		}
	};
</script>

<style>
	.message {
		text-align: center;
		margin-top:50%;
	}
</style>