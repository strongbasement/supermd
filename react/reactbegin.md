### esxtension names 
``` #es7 react redux ```


### react routes

#### inside react index.js


![alt text](image.png)





#### inside app.js

![alt text](image-1.png)

### inside  router dont forget about exact


![alt text](image-2.png)


### routes v6 updated codes

``` js inside app.js

import { useState } from 'react'
import { Link } from 'react-router-dom'
import {Route,Routes} from 'react-router-dom'
import Home from './Home'
import About from './About'
import Contact from './Contact'

import Instanav from 'Instanav/src/Instanav'
function App() {
 
  return (
    <>
     <header>

      <Instanav navdata={[{link:'/',text:'Home'},{link:'/about',text:'About'},{link:'/contact',text:'Contact'}]}/>
        {/* <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/about">About</Link>
            </li>
            <li>
              <Link to="/contact">Contact</Link>
            </li>
          </ul>
        </nav>
        <hr
      />  */}
     </header>
      <main>
        <Routes>
          <Route  path="/" element={<Home />} />
          <Route path="/about" element={<About />} />
          <Route path="/contact" element={<Contact />} />
        </Routes>
        </main>
        <footer>copyrights</footer>
    </>
  )
}

export default App


````


### inside main.js

``` js
import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import App from './App.jsx'
import { BrowserRouter as Router} from 'react-router-dom'
createRoot(document.getElementById('root')).render(
  <StrictMode>
    <Router>
      
        
        
        
        <App />
     
      
      
    </Router>
  </StrictMode>,
)



```