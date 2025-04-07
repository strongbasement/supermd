# context

```js

import { createContext } from "react";
import useWindowSize from '../hooks/useWindowSize';

const Datacontext = createContext({});

export const DataProvider = ({ children }) => {
    const { width } = useWindowSize();

    return (
        <Datacontext.Provider value={{ width }}>
            {children}
        </Datacontext.Provider>
    );
};

export default Datacontext;


```


# usecontext


``` js


import {useContext } from 'react';
import {Datacontext} from 'react';


```
