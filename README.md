<h1 style="text-align: center">React Native Components</h1>
Cross platform react native components

<div style="text-align: center">
  <img src="https://badgen.net/badge/node@LTS/>=12.11.1/green">
  <img src="https://badgen.net/badge/npm/>=5.6.0/blue">
  <img src="https://badgen.net/badge/react-native/>=0.60/orange">
  <img src="https://badgen.net/badge/code style/standard/yellow">
  <img src="https://badgen.net/badge/release/v1.0.0/pink">
</div>

## Getting Started

### Prerequisites

`NodeJS >= v12.11.1`
`react-native-cli >= 2.0.1`
`react-native >= 0.61`
`npm >= 5.6.0`

## Table of Contents

- [Install](#install)
- [Components](#components)
- [License](#license)

## Install

npm:

```sh
npm install react-native-ui-modules
```

yarn:

```sh
yarn add react-native-ui-modules
```

## Components

- Input

This component inherits all native TextInput props along with the following:-

| Property          | Type                                  |
| ----------------- | ------------------------------------- |
| variant           | String(enum - "outlined", "standard") |
| multiline         | Boolean                               |
| inputWidth        | String                                |
| height            | Number                                |
| borderRadius      | Number                                |
| borderColor       | String                                |
| borderBottomColor | String                                |

```js
import React from "react";
import { Input } from "react-native-ui-modules";

const InputComponent = () => {
  return <Input variant="outlined" inputWidth="85%" placeholder="Username" />;
};
```

- Spinner

| Property        | Type                            |
| --------------- | ------------------------------- |
| visible         | Boolean                         |
| size            | String(enum - "small", "large") |
| backgroundColor | String                          |
| onClose         | Function                        |
| color           | String                          |

```js
import React, { useState } from "react";
import { Spinner } from "react-native-ui-modules";
import { View, Button, StyleSheet } from "react-native";

const SpinnerComponent = () => {
  const [visible, setSpinner] = useState(false);
  const toggleSpinner = () => {
    setSpinner(!visible);
  };

  return (
    <View style={styles.container}>
      <Button title="Show spinner" onPress={toggleSpinner} />
      <Spinner
        color="red"
        size="small"
        backgroundColor="#FFF"
        visible={visible}
        onClose={toggleSpinner}
      />
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: "center",
    justifyContent: "center",
    backgroundColor: "#FFF",
  },
});
```

- Snackbar

| Property         | Type                           |
| ---------------- | ------------------------------ |
| visible          | Boolean                        |
| position         | String(enum - "top", "bottom") |
| message          | String                         |
| messageTextColor | String                         |
| actionText       | String                         |
| actionTextColor  | String                         |
| backgroundColor  | String                         |
| handleAction     | Function                       |

```js
import React, { useState } from "react";
import { Snackbar } from "react-native-ui-modules";
import { View, Button, StyleSheet } from "react-native";

const SnackbarComponent = () => {
  const [visible, setSnackbar] = useState(false);
  const toggleSnackbar = () => {
    setSnackbar(!visible);
  };

  return (
    <View style={styles.container}>
      <Button title="Show snackbar" onPress={toggleSnackbar} />
      <Snackbar
        position="top"
        actionText="Close"
        message="Snackbar message"
        visible={visible}
        backgroundColor="#000000"
        messageTextColor="#FFFFFF"
        actionTextColor="#AB2611"
        handleAction={toggleSnackbar}
      />
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    alignItems: "center",
    justifyContent: "center",
    backgroundColor: "#FFF",
  },
});
```

## License

[MIT](LICENSE) © Ajay
