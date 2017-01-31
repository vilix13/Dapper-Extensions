# Introduction

This is my fork of https://github.com/tmsmith/Dapper-Extensions

For my proposes I added functionality which allows you make Update with Dapper-Extensions only selected props (fields).

Any tips to improve the code are welcome through issues and PR.

Now I noticed that a working build for only DapperExtensions.Net45

# Examples:

```
public class Person
{
  public int Id {get; set;},
  public string Name {get; set;},
  public string Phone {get; set;},
  public DateTime CreatedAt {get;set;}
}

//Anonymous type API:
db.Update<Person>(new { Id = 1, Name = "Jon Biceps" }); // Update only 'Name' field of Person with id == 1. 

//string array API:
db.Update<Person>(new Person() 
  {
    Id = 1,
    Name = "Jon Biceps"
  }, 
  propsToUpdate: new string[] {"Name"}); //Do same as above
```

#Warning
**Now it is dirty dev version! But its work. Use at your own risk.
My changes does not contain any validators, if pass no valid argument - you receive an unhandled exception.

#Plans to future
- Move code in the procedure In accordance with the Dapper style guide
- Cover code with tests
- PR to original repo.
