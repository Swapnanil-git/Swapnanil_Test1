# Swapnanil_Test1

1. const[user,setUser] = useState<User| null>(null)>  // This is the right syntax
2. In useEffect the dependancy should be [userId], because on an empty dependancy array it will only execute when the component in mounted, if user ID is changed, it wont have any effect
3. more error handling should be there in useEffect. examples -
if (!response.ok) -> Failed to fetch
4. An interface for User is suggested to avoid type errors.
5. Async programming is preferrable inside the useEffect.
   useEffect(()=>{
    const fetchUser = async()=>{
        try{

        }catch(err){

        }
    }
   })
6. We can use more states like Loading or error for UI level error handling. 

7. Passing fetcher as a prop to the component will help in testing as we can replace this with another function when no real network call is needed.

type Props= {
    userId:number;
    fetcher?: typeof fetch;
}

useEffect (()=>{
    fetcher(`https://api.com/user/${userId}`)
})

if in future this fetch is needed to be changed into axios then we can just pass axios to fetcher.

8. It is a good practice to maintai separate states of user, loading and error.

9. Raw server errors should not be exposed to user, rather use a fallback UI for a friendly message.

// TEST CASE REVIEW:-

1. The test is missing success and error cases.
2. Unit test is required to render user data on success.
3. A test is required for the fallback UI if the bio is missing.
4. Suggestion for a test to confirm that the loading indicator disappears after success.
5. If userId is added in the useEffect dependancy, a test is required to confirm refetch when userId changes.