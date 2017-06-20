# react-native-soluti-date-picker

  - Cross-platform library writen only in JS
  - Uses DatePickerIOS for iOS
  - Uses DatePickerAndroid and TimePickerAndroid for Android

### Installation

```bash
npm i --save "link to git repo"
```

## Usage

```javascript
import React from "react";
import {View, Text, StyleSheet, TouchableOpacity} from "react-native";
import DateTimePicker from "./test/date-time-picker";

export default class App extends React.Component {

  constructor(props) {
    super(props);

    this.state = {
      selectedDate: null,
      selectedTime: null,
      selectedDateTime: null,
    };
  }

  render() {
    return (
      <View style={[styles.rootView]}>
        <TouchableOpacity
          style={[styles.button]}
          onPress={() => {this.datePicker.show();}}
        >
          <Text
            style={[styles.text]}
          >
            {"Selected Date is: \n" + (this.state.selectedDate || "N/A - Tap to select")}
          </Text>
          <DateTimePicker
            type="date"
            selectedDate={new Date()}
            is24Hour={false}
            ref={(ref) => {this.datePicker = ref;}}
            onSelectDate={(date) => {this.setState({selectedDate: date});}}
          />
        </TouchableOpacity>

        <TouchableOpacity
          style={[styles.button]}
          onPress={() => {this.timePicker.show();}}
        >
          <Text
            style={[styles.text]}
          >
            {"Selected Time is: \n" + (this.state.selectedTime || "N/A - Tap to select")}
          </Text>
          <DateTimePicker
            type="time"
            selectedDate={new Date()}
            is24Hour={false}
            ref={(ref) => {this.timePicker = ref;}}
            onSelectDate={(date) => {this.setState({selectedTime: date});}}
          />
        </TouchableOpacity>

        <TouchableOpacity
          style={[styles.button]}
          onPress={() => {this.dateTimePicker.show();}}
        >
          <Text
            style={[styles.text]}
          >
            {"Selected DateTime is: \n" + (this.state.selectedDateTime || "N/A - Tap to select")}
          </Text>
          <DateTimePicker
            type="datetime"
            selectedDate={new Date()}
            is24Hour={false}
            ref={(ref) => {this.dateTimePicker = ref;}}
            onSelectDate={(date) => {this.setState({selectedDateTime: date});}}
          />
        </TouchableOpacity>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  rootView: {
    position: "absolute",
    left: 0,
    top: 0,
    right: 0,
    bottom: 0,
    justifyContent: "center",
    alignItems: "center",
    padding: 15,
  },
  button: {
    marginTop: 30,
    justifyContent: "center",
    alignItems: "center",
  },
  text: {
    textAlign: "center",
  }
});
```

## Example

Demo project in the `exemple` folder

## Props

| Prop | iOS | Android | Value |
| ------------- | ------------- | ------------- | ------------- | 
| type | Yes | Yes | One of `date`, `time`, `datetime` |
| selectedDate | Yes | Yes | `Date` |
| minDate | Yes | Yes | `Date` |
| maxDate | Yes | Yes | `Date` |
| onSelectDate | Yes | Yes | `function` - with two parameters, `date` and `dateAsUtc`|
| is24Hour | No | Yes | `boolean` |
| iosCancelButtonTitle | Yes | No | `String` |
| iosDoneButtonTitle | Yes | No | `String` |
| iosBackgroundStyle | Yes | No | `StyleSheet` |
| iosActionBarStyle | Yes | No | `StyleSheet` |
| iosActionBarCancelButtonStyle | Yes | No | `StyleSheet` |
| iosActionBarCancelTextStyle | Yes | No | `StyleSheet` |
| iosActionBarDoneButtonStyle | Yes | No | `StyleSheet` |
| iosActionBarDoneTextStyle | Yes | No | `StyleSheet` |
| iosSeparatorStyle | Yes | No | `StyleSheet` |
| iosPickerStyle | Yes | No | `StyleSheet` |
