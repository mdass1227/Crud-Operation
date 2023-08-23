import { useEffect,useState } from "react"
import axios from "axios";


export default function App() {
  const [user,setUser] =useState([]);
  useEffect(()=> {
    axios.get('https://jsonplaceholder.typicode.com/users')
    .then(res => setUser(res.data))
  })
  

  return (
    <div className="app">
      {user.map(u=>(
        <div>
          {u.name}{u.email}{u.id}
        </div>
      ))}

      

    </div>
  )
}
