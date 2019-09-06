 #  React Native Quidpay WebView  

  
This is the react native SDK for Quidpay By [Quidpay.](https://quidpay.io/)


💸💳The package allows you accept payment using Quidpay  and guess what , it doesn't require any form of linking, just install and begin to use .

### Compatibility

Our release cycle is independent of  `react-native`. We follow semver and here is the compatibility table:

|`@react-native-community/cli` |`react-native`|
| --| --|
|[^1.0.0](https://github.com/react-native-community/cli/tree/1.x) |^0.59.0|

## Table Of Content

-   [Getting Started](https://github.com/react-native-nigeria/react-native-quidpay-webview#getting-started)
-   [Installations](https://github.com/react-native-nigeria/react-native-quidpay-webview#installations)
-   [Deployment](https://github.com/react-native-nigeria/react-native-quidpay-webview#deployment)
-   [How It Works](https://github.com/react-native-nigeria/react-native-quidpay-webview#how-it-works)
 -   [Usage](https://github.com/react-native-nigeria/react-native-quidpay-webview#usage)
-   [API](https://github.com/react-native-nigeria/react-native-quidpay-webview#API)
 
-   [Contributions](https://github.com/react-native-nigeria/react-native-quidpay-webview#contributions)  

## Getting Started

### [](https://github.com/react-native-nigeria/react-native-quidpay-webview#prerequisites)Prerequisites

-   [Quidpay Public And Encryption Keys](https://quidpay.io)

-   [Node](https://nodejs.org/en/)
-   [NPM](https://www.npmjs.com/get-npm)
-   [React Native](https://facebook.github.io/react-native/docs/getting-started.html)

## Installations

> To use  react native quidpay webview in your application, you need to have  `Node`  and  `npm`  downloaded and installed on your machine.

-   [Click Here](https://nodejs.org/en/)  to download and install  `Node`  to your machine,  `npm`  is always automatically installed when you install  `Node`.
    
-   To ensure you have  `Node`  and  `npm`  installed, enter the following command into your terminal/command prompt  `node -v`  and  `npm -v`  respectively.
    
-   To run  `react native`  on your machine you can use  `npm install -g expo-cli`  to install  [Expo CLI](https://expo.io/)  a command line utility to get you started quickly or use this command  `npm install -g react-native-cli`  to install the  [react native CLI](https://facebook.github.io/react-native/docs/getting-started.html).
 
 ## Deployment

 To Implement QuidPay easily with React Native

-   You can get your Public, Secret and your Encryption Keys on your account by clicking this link >>>[Quidpay Live](https://dashboard.quidpay.io/dashboard/settings/apis).
    
-   To get your  **`TEST`**  public, secret and encryption keys click on the  `Live Mode`  Toggle button to switch to Test account and  `Test Mode`  Toggle button to switch to live.
    

## How It Works

This is a simple demonstration of how to set up a simple react native app and integrate  `Quidpay inline payment in react native` 

Using the  [Expo CLI](https://expo.io/)  command line utility, Enter the following command to get started:

-   `expo init AwesomeProject`
    
-   `cd AwesomeProject`
    
-   `npm start`
    
-   You should get this from your terminal:
![enter image description here](https://camo.githubusercontent.com/04aebd14deccd6d8501c80699820588ca8e7d402/68747470733a2f2f7265732e636c6f7564696e6172792e636f6d2f666c757474657277617665646576656c6f7065722f696d6167652f75706c6f61642f76313534303735323736352f726176652d72656163742d6e61746976652f6578706f2d626172636f64652e706e67)

-   Install the Expo client or mobile application from  [Apple Store](https://itunes.apple.com/app/apple-store/id982107779)  or  [Playstore](https://play.google.com/store/apps/details?id=host.exp.exponent&referrer=www)
    
-   Open the Expo client app you installed on your mobile phone, then scan the barcode displaying on the terminal on your PC.
    
-   If successfully scanned and built, your app should load up on your mobile phone with the result in the image below;
![enter image description here](https://camo.githubusercontent.com/d3f07cc60a92d90f98883ddec9f9852aa8c4cc5e/68747470733a2f2f7265732e636c6f7564696e6172792e636f6d2f666c757474657277617665646576656c6f7065722f696d6167652f75706c6f61642f76313534303735323736342f726176652d72656163742d6e61746976652f6170702d776f726b696e672e706e67)

### Integrating Rave React Native

You can pull in react-native-rave-webview into app with the steps below;

-   Change directory into your current project directory from your terminal and enter this command:
    
    `npm install react-native-quidpay-webview --save`
    
    ### [](https://github.com/react-native-nigeria/react-native-rave-webview#or)OR
    
    `yarn add react-native-quidpay-webview`
    
 and that's it, you're all good to go!

  
  `Note:`  To use  `Yarn`  on your machine  [Click Here](https://yarnpkg.com/en/docs/install)

## Usage

### [](https://github.com/react-native-nigeria/react-native-rave-webview#payments)Payments

#### [](https://github.com/react-native-nigeria/react-native-rave-webview#1--import-rave-component)1. import Rave Component

    import {Quidpay} from 'react-native-quidpay-webview';

 #### 2. Set your success, failure and close methods

```javascript
      onSuccess(data) {
        console.log("success", data);
        // You can get the transaction reference from successful transaction charge response returned and handle your transaction `		verification here
    
      }
    
      onCancel() {
        console.log("error", 'Transaction was Cancelled!');
      }
    
      onError() {
        //an error occoured 
    
      }
 ``` 
#### 3. Use component (ensure to set currency for the desired payment method to display)

 ```javascript
   render() {
    return (
       <View  style={styles.container}>
         <Quidpay
           buttonText=  "Pay Now"
           QuidpayKey="<your-api-key-here>"
           amount={20000}
           billingEmail="ayoshokz@gmail.com"
       	  billingMobile="08101****"
           billingName="Oluwatobi Shokunbi"
           ActivityIndicatorColor="green"
           onCancel={()=>this.onCancel()}
           onSuccess={(transactionRef)=>this.onSuccess(transactionRef)}
           btnStyles={{backgroundColor:'green', width:100, alignContent:  'center' }}
           textStyles={{ color:'white', alignSelf:  'center', }}
           onError={()=>{alert('something went wrong')}}
           txref="1234"
        />
    </View>
  );
  }
 ```

  
  
## API's

  

#### [](https://github.com/react-native-nigeria/react-native-quidpay-webview#API)all React-Native-Quidpay-WebView API

  

| Name | use/description | extra |
| :--- | :---: | ---: |
| `buttonText` | Defines text on the button | default: `Pay Now` |
| `textStyles` | Defines styles for text in button | `nill` |
| `btnStyles` | Defines style for button | `nill` |
| `QuidpayKey` | Public or Private paystack key(visit quidpay.io to get yours) |`nill` |
| `amount` | Amount to be paid | `nill` |
| `txref` | set TransactionRef of transaction | `nill` |
| `ActivityIndicatorColor` | color of loader | default: `green` |
| `billingEmail` | Billers email | default: `nill` |
| `billingMobile` | Billers mobile | default: `nill` |
| `billingName` | Billers Name | default: `nill` |
| `onCancel` | callback function if user cancels | default: `nill` |
| `onSuccess` | callback function if transaction was successful (it will also return the transactionRef number in the callback ) | default: `nill` |
| `onError` | callback function if an error occured during transaction  | default: `nill` |

  

## [](https://github.com/react-native-nigeria/react-native-quidpay-webview#contributions)Contributions

  

What to help make this package even more awesome? [Read how to contribute](https://github.com/react-native-nigeria/react-native-quidpay-webview/blob/master/contribution.md)



## [](https://github.com/react-native-nigeria/react-native-quidpay-webview#licensing)Licensing

  This project is licensed under MIT license.
## Related Projects
- [React-Native-Paystack-WebView](https://github.com/just1and0/react-native-paystack-webview)
-  [React-Native-rave-WebView](https://github.com/react-native-nigeria/react-native-rave-webview)



  
  

### Don't forget to star, like and share :)
