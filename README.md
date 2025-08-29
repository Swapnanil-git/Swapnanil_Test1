# Swapnanil_Test1

1. const[user,setUser] = useState<User| null>(null)>  // This is the right syntax
2. In useEffect the dependancy should be [userId], because on an empty dependancy array it will only execute when the component in mounted, if user ID is changed, it wont have any effect
3. more error handling should be there in useEffect. examples -
if (!response.ok) -> Failed to fetch
4. Async programming is preferrable inside the useEffect.
   useEffect(()=>{
    const fetchUser = async()=>{
        try{

        }catch(err){

        }
    }
   })
5. We can use more states like Loading or error for UI level error handling. 