# rn-universal-auth0

This repo is based on one of Auth0's starter apps that use react-native-auth0 SDK to surface the Universal Login web modal on native devices.

## Overview

The Auth0 web modal built in to react-native-auth0 SDK is not very native, as such this repo endeavours to implement a react native webview that seemlessly surfaces the universal login experience to the end user.

## 1. Install

Clone the repository and install the dependencies with [Yarn](https://yarnpkg.com):

```bash
yarn install
```

### iOS Applications Only

Change the directory into the `ios` folder and run the following command to install the SDK pod with [CocoaPods](https://cocoapods.org/):

```bash
cd ios
pod install
```

or 

```bash
npx pod-install
```

You should see the `A0Auth0` pod being installed and linked to the sample app.

> As a proof of concept, this app will only be configured for iOS.

## 2. Configure Auth0

1. Copy the `app/auth0-configuration.js.example` in this sample to `app/auth0-configuration.js`.
2. Open your [Applications in the Auth0 dashboard](https://manage.auth0.com/#/applications).
3. Select your existing Application from the list or click **Create Application** at the top to create a new Application of type **Native**.
4. On the **Settings** tab for the Application, copy the "Client ID" and "Domain" values and paste them into the `app/auth0-configuration.js` file created above.
5. In the **Allowed Callback URLs** field, paste in the text below and replace `YOUR_DOMAIN` with the **Domain** from above. These URLs are required for the authentication result to be redirected from the browser to the app:

```
com.auth0samples://YOUR_DOMAIN/ios/com.auth0samples/callback,
com.auth0samples://YOUR_DOMAIN/android/com.auth0samples/callback
```

6. Add the same values to the **Allowed Logout URLs** field as well. These are required for the browser to redirect back to the app after the user logs out.
7. Scroll down and click **Save Changes**.

## 3. Run The App

Run your app on an emulator, simulator, or your own connected device.

- To run the app on iOS run `yarn run ios`.
- To run the app on Android run `yarn run android`.

The first run may take a while to fully launch. Keep an eye out for confirmation windows and watch the terminal for output and results.

**Note:** If you get an error about "No bundle URL present" try clicking reload in the app or running `yarn run ios` again.
