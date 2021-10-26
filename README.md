# SDP-1
Firstly we conducted a online survey on Rental System using google forms. 
From that problems we identified is many people are suffering while transporting from that we concluded that we have to create Bike Rental System.Everyone can easily pay the rents and can travel every where.
We created Customer Journey map, Personas, Insights, Modules, Prototype.
Now are developing a webpage on Bike Rental System using MERN, with the knowledge of design thinking and Project Development

# Login.js- in react
import React from 'react'
import image1 from './image2.jpg'
import './xyz.css'
import Navbar from './Navbar'
import ForgotPassword from './ForgotPassword'
import SignUp from './SignUp'

import {BrowserRouter,Route} from 'react-router-dom'

export default function Login()
{
    return <div>
    <div class="image4">
    <div className="main">
    <div className="sub-main">
    <div>
    <div className="img">
    <div className="image">
    <img src={image1} alt="profile" className="profile"/>
    </div>
    </div>
    <div>
        <p></p>
    <div>
   <input type="text" placeholder="Enter username or email" className="name"/>
    </div>
    <div className="second-input"/>
     <div>                     
   <input type="password" placeholder="Enter password" className="name"/>
   </div>
     <div className="login-button">
   <button><b>Login</b></button>
     </div>
      </div>
      <center>
      <BrowserRouter>
     <Navbar/>
    
    
    <Route path="/forgotpassword" component={ForgotPassword} exact/>
    <Route path="/signup" component={SignUp} exact/>
    </BrowserRouter>
    </center>
        </div>
          </div>
          </div>
      </div>
     </div>
 }
 
 # Navbar.js
 import React from 'react'

import {Link} from 'react-router-dom'

export default function Navbar()
{
    return <div>
         <ul>
       <Link to="/forgotpassword">
<li>ForgotPassword</li>
</Link> 
       
      <Link to="/signup">
      <li>SignUp</li>
      </Link>     
        </ul>
    </div>
} 

# ForgotPassword.js
import React from 'react';
import './xyz.css'
import {useState} from 'react'

export default function ForgotPassword()
{
    const[email,setemail] = useState("")
   
    function displayvalues()
    {
        var user = {
            
            email:email,
        }
        console.log(user)
    }
    return <div className="forgot">
        <form onSubmit={displayvalues}>
            <br/>
      Enter Email:  <input type="email" placeholder="Enter Email" value={email} required onChange={ (e) => {setemail(e.target.value)}}/><br/><br/>
        
         <input type="submit" className="submit" value="Submit"/>
         
         </form>
    </div>
}

# SignUp.js
import React from 'react';
import './xyz.css';
import {useState} from 'react'

export default function SignUp()
{
    const[firstname,setfirstname] = useState("")
    const[username,setusername] = useState("")
    const[gender,setgender] = useState("")
    const[age,setage] = useState("")
    const[password,setpassword] = useState("")
    function displayvalues()
    {
        var user = {
            
            firstname:firstname,
            username:username,
            gender:gender,
            age:age,
            password:password
        }
        console.log(user)
    }
    return <div className="sign">
        <form onSubmit={displayvalues}>
            <br/>
         Enter Fullname:  <input type="text" placeholder="Enter Full name" value={firstname} required onChange={ (e) => {setfirstname(e.target.value)}}/><br/><br/>
        Create UserName:  <input type="text" placeholder="Enter Username" value={username} required onChange={ (e) => {setusername(e.target.value)}}/><br/><br/>
      Gender:   <input type="radio" className="radio-button"value="Male" required name="gender"onClick={ (e) => {setgender(e.target.value)}}/>Male
       <input type="radio" className="radio-button" required name="gender" value="Female" onClick={ (e) => {setgender(e.target.value)}}/>Female <br/><br/>
        Enter DOB :  <input type="dob" placeholder="DD/MM/YYYY" required value={age} onChange={ (e) => {setage(e.target.value)}}/><br/><br/>
 Create Password: <input type="password" placeholder="Enter Password" required value={password} onChange={ (e) => {setpassword(e.target.value)}}/><br/><br/>
         <input type="submit" className="submit" value="Register"/><br/> <br/>
         <input type="reset" className="clear" value="Clear"/>
         </form>
    </div>
}
