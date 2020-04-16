"# .netcore-learning"

# Basic Web API Routing
```csharp
[Route("api/[controller]")]
[ApiController]
public class UserController: Controller
{
    // use param as path
    //api/User/checkin/I%20liked
    [HttpPost("checkin/{LateReason}")]
    public async Task<string> test1(String LateReason){
        // await handling
        // return a string
    }
    //api/User/checkout
    [HttpGet("checkout")]
    public string test2()
    {
        return "{\"test1\":4321}";
    }

}
```
+ Note
    * test1, test2 function must public
    * *{**LateReason** }* is same name with *(String **LateResaon**)*
    * POST or GET but both must follow standard format route of web api 

# Routing with multiple params 


# Get params with Binding feature of .netcore 