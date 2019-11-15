
# react unified
A library for unified ui in react.js

## Installation
Run the following command:

`npm i react-unified react-native-gesture-handler`

`react-native link react-native-gesture-handler`

## Css

```jsx

// before:
function WebComponent() {

    return (
        <div id={'selector'}>
            <style>
                #selector {
                    background-color: white;
                }
                #selector:hover {
                    background-color: blue;
                }
                #selector:active {
                    background-color: red;
                }
                #selector:focus {
                    background-color: yellow;
                }
            </style>
        </div>
    );
}

// after:
import React, {useRef} from 'react';
import {View, useHover, useActive, useFocus} from 'react-unified';

function UnifiedComponent() {

    const selectorRef = useRef(null);
    
    const hover  = useHover(selectorRef);
    const active = useActive(selectorRef);
    const focus  = useFocus(selectorRef);

    return (
        <View 
            ref={selectorRef}
            style={{
                backgroundColor: hover ? 'blue' : active ? 'red' : focus ? 'yellow' : 'white',
            }}
        />
    );
}
```
