<pre>
  import React, {useRef, useState , useEffect, createContext} from 'react';
import ReactDom from "react-dom/client";
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.bundle.min';
import "./index.css"
import Tos from "./tom1"
import Tos2 from "./tom2"

  var createcon = createContext();
function X(){

  var [number, setnumber] = useState(0);

  useEffect(()=>{
    console.log("applyed");
    },[number])

  return(
  <div>
  <h2 className='text-center'>{number}</h2>
  <button  className='btn btn-primary' onClick={() => {
    setnumber(number+1)
  }}>click </button>
  <createcon.Provider value={number}>
    <Tos />
  </createcon.Provider>

<createcon.Provider value={number}>
  <Tos2 />
  </createcon.Provider>

  </div>
  )
}

const root = ReactDom.createRoot(document.getElementById('root'));
root.render(<X />);

export default X
export { createcon };
</pre>

















<pre>
import React, { useEffect ,useContext, useRef} from "react";
import ReactDom from "react-dom/client"
import { createcon } from "./index"


function Tos2(){

    
var ref = useRef(0);

    useEffect(()=>{
    ref.current.style.color = "red";
    console.log(ref.current);
},[])


    var data = useContext(createcon);
    return (
        <>
        <h1 ref={ref}> TOs 2: {data}</h1>
        </>
    )
}


export default Tos2;
  
</pre>
