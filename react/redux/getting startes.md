#### installing redux

```
npm install @reduxjs/toolkit react-redux

```

#### craete folder called app inside src then inside app folder create store.js


### inside store.js


```js
import {configureStore} from '@reduxjs/toolkit'
export const store=configureStore({
    reducer:{
        
    }
})

```


### main.jsx should be look like this


``` js

import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import { store } from './app/store'
import {Provider} from 'react-redux'

createRoot(document.getElementById('root')).render(
  <StrictMode>
    <Provider store={store}>
    <App />
      </Provider>  
    
  </StrictMode>,
)



```


###  inside src create features folder inside features create another directory counter and insite it create counterSlice.js,inside counterslice.js



```js

import { createSlice } from "@reduxjs/toolkit";
const initialState={
count:0
}

export const counterSlice=createSlice({
    name:'counter',
    initialState,
    reducers:{
        increment:(state)=>{
            state.count+=1;
        },
        decrement:(state)=>{
            state.count-=1;
        }

    }
});


export const {increment,decrement}=counterSlice.actions;
export default counterSlice.reducer;



```


#### now update the store.js


``` js

import {configureStore} from '@reduxjs/toolkit'
import counterReducer from '../features/counter/counterSlice'

export const store=configureStore({
    reducer:{
counter:counterReducer
    }
})

```


### createcounter counter componeny inside counter folder like Counter.jsx,inside counter .js write below code


``` js

import React from 'react'
import { useSelector,useDispatch } from 'react-redux'
import { increment,decrement } from './counterSlice'
const Counter = () => {
    const count=useSelector((state)=>state.counter.count);
    const dispatch=useDispatch();
  return (
    <div>
      <section>
        <p>{count}</p>
   <button onClick={()=>dispatch(increment())}>+</button>
   <button onClick={()=>dispatch(decrement())}>-</button>
      </section>
    </div>
  )
}

export default Counter


```

### adding two more function in counterSlice.js

``` js

import { createSlice } from "@reduxjs/toolkit";
const initialState={
count:0
}

export const counterSlice=createSlice({
    name:'counter',
    initialState,
    reducers:{
        increment:(state)=>{
            state.count+=1;
        },
        decrement:(state)=>{
            state.count-=1;
        },
        reset:(state)=>{
state.count=0;
        },
        Addamount:(state,action)=>{
state.count+=action.payload;
        }


    }
});


export const {increment,decrement,reset,Addamount}=counterSlice.actions;
export default counterSlice.reducer;


```
#### use this inside Counter.jsx



``` js


import React from 'react'
import { useSelector,useDispatch } from 'react-redux'
import { increment,decrement ,reset,Addamount} from './counterSlice'
import { useState } from 'react';
const Counter = () => {
    const count=useSelector((state)=>state.counter.count);
    const dispatch=useDispatch();
    const [addamounts,setaddamounts]=useState(0);
    const addvalue=Number(addamounts)||0;
    const resetall=()=>{
      dispatch(reset());
      setaddamounts(0);
    }
  return (
    <div>
      <section>
        <p>{count}</p>
   <button onClick={()=>dispatch(increment())}>+</button>
   <button onClick={()=>dispatch(decrement())}>-</button>
   <input type="text" value={addamounts} onChange={(e)=>setaddamounts(e.target.value)} />

   <button onClick={()=>dispatch(Addamount(addvalue))}>Addamount</button>
   <button onClick={()=>resetall()}>reset</button>

      </section>
    </div>
  )
}

export default Counter


```