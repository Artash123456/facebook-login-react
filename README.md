> A Component React for Facebook Login

## Getting Started

- `yarn add facebook-login-react` or `npm install facebook-login-react`
- Your application will also need `react-dom` and `react` installed.

## How to use

### Basic button with styling

```js
import React from "react";
import ReactDOM from "react-dom";
import { FacebookLogin } from "facebook-login-react";

const responseFacebook = (response) => {
  console.log(response);
};

ReactDOM.render(
  <FacebookLogin
    appId="1088597931155576"
    autoLoad={true}
    fields="name,email,picture"
    onClick={componentClicked}
    callback={responseFacebook}
  />,
  document.getElementById("demo")
);
```

The `render` function will be passed the following properties for you to use:

- `onClick`
- `isDisabled`
- `isProcessing`
- `isSdkLoaded`

### Custom CSS Class and Icon

By default fontawesome is included, If you don't want to use default fontawesome icons, you can send an element in icon attribute

Fontawesome example:

```js
import React from "react";
import ReactDOM from "react-dom";
import { FacebookLogin } from "facebook-login-react";

const responseFacebook = (response) => {
  console.log(response);
};

ReactDOM.render(
  <FacebookLogin
    appId="YOUR_APP_ID"
    autoLoad={true}
    fields="name,email,picture"
    callback={responseFacebook}
    cssClass="my-facebook-button-class"
    icon="fa-facebook"
  />,
  document.getElementById("demo")
);
```

Custom element example:

```js
import React from "react";
import ReactDOM from "react-dom";
import { FacebookLogin } from "facebook-login-react";
import TiSocialFacebookCircular from "react-icons/lib/ti/social-facebook-circular";

const responseFacebook = (response) => {
  console.log(response);
};

ReactDOM.render(
  <FacebookLogin
    appId="YOUR_APP_ID"
    autoLoad={true}
    fields="name,email,picture"
    callback={responseFacebook}
    cssClass="my-facebook-button-class"
    icon={<TiSocialFacebookCircular />}
  />,
  document.getElementById("demo")
);
```

### Custom permission

By default the component, request only 'public_profile' permission, you can change if you send 'scope', that is a string comma separated attribute.

see https://developers.facebook.com/docs/facebook-login/permissions for permissions list

```js
import React from "react";
import { FacebookLogin } from "facebook-login-react";

class MyComponent extends React.Component {
  responseFacebook(response) {
    console.log(response);
  }

  render() {
    return (
      <FacebookLogin
        appId="YOUR_APP_ID"
        autoLoad={true}
        fields="name,email,picture"
        scope="public_profile,user_friends,user_actions.books"
        callback={this.responseFacebook}
      />
    );
  }
}

export default MyComponent;
```

### Server

```js
"use strict";

import React from "react";
import { FacebookLogin } from "facebook-login-react";

class MyComponent extends React.Component {
  responseFacebook(response) {
    console.log(response);
  }

  render() {
    return (
      <FacebookLogin
        appId="YOUR_APP_ID"
        autoLoad={true}
        fields="name,email,picture"
        callback={this.responseFacebook}
      />
    );
  }
}

export default MyComponent;
```

## Parameters

|        params         |  value   |                                                                                                default value                                                                                                |
| :-------------------: | :------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | ------------------------------------------------------ |
|         appId         |  string  |                                                                                                  Required                                                                                                   |
|         size          |  string  |                                                                                           small - medium - metro                                                                                            |
|         scope         |  string  |                                                                                    public_profile, email, user_birthday                                                                                     |
|        fields         |  string  |                                                                                             name,email,picture                                                                                              |
|       callback        | function |                                                                                             resultFacebookLogin                                                                                             |
|     returnScopes      | boolean  |                                                                                                    false                                                                                                    |
|       autoLoad        | boolean  |                                                                                                    false                                                                                                    |
|         xfbml         | boolean  |                                                                                                    false                                                                                                    |
|        cookie         | boolean  |                                                                                                    false                                                                                                    |
|      textButton       |  string  |                                                                                             Login with Facebook                                                                                             |
|       cssClass        |  string  |                                                                             kep-login-facebook kep-login-facebook-[button-size]                                                                             |
|      redirectUri      |  string  |                                                                                     window.location.href (mobile-only)                                                                                      |
|        version        |  string  |                                                                                                     3.1                                                                                                     |
|         icon          |  string  |                                                                                                   element                                                                                                   | none                                                   |
|       language        |  string  |                                                                                                    en_US                                                                                                    |
|        onClick        | function |                                                                                       Initial click on the component                                                                                        |
|       isMobile        | boolean  |                                                                                           detected via userAgent                                                                                            |
| disableMobileRedirect | boolean  |                                                                                                    false                                                                                                    | set to true for popup authentication on mobile devices |
|      isDisabled       | boolean  |                                                                                                  undefined                                                                                                  |
|          tag          |  string  |                                                                                       HTML Element, Ex: 'a', 'button'                                                                                       |
|       onFailure       | function |                                                                               optional function to separatere the failed init                                                                               |
|         state         |  string  | optional string to maintain state between the request and callback. This parameter should be used for preventing Cross-site Request Forgery and will be passed back to you, unchanged, in your redirect URI |
|       authType        |  string  |                                                                                optional string to change authentication type                                                                                |
|     responseType      |  string  |                                                                      optional string to change response type. Default value is 'code'                                                                       |
"# facebook-login-react" 
"# facebook-login-react" 
