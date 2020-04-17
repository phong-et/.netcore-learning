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
    * Need research more Object params controller function
    * POST or GET but both must follow standard format route of web api.

# Default Routing & Default Endpoint
```csharp
[Route("api/[controller]")]
[ApiController]
public class UserController: Controller
{
    //[HttpPost]
    public string test1() => "{\"test1\":1111}";
    [HttpGet]
    public string test2() => "{\"test2\":2222}";
    [HttpGet]
    public string test3() => "{\"test3\":3333}";
}
```
+ Result :
    * Default Routing is : /api/user (all endpoints without sub route)
    * Default method of endpoint is POST (test1 without [HttpPost] header)
    * curl GET api/user 
        - show error because two endpoints is same route
        - resolve by naming route endpoint, ensure each endpoint has only one route, e.g :
            ```csharp
                // api/user/test2
                [HttpGet("test2")]
                public string test2() => "{\"test2\":2222}";
                // api/user/test3
                [HttpGet("test3")]
                public string test3() => "{\"test3\":3333}";
            ``` 

    * curl POST api/user 
        reuturn **{\"test1\":1111}**

# Get params with Binding feature of .netcore 


# Entity Framework Core (EF Core)
* Create Migration
    * Create Models

    * Generate migration files

* Create Seeder


* Migrate Models(Table, Primary Key, e.g ... ect)

* Insert data to Tables (Seeding)