# BlackstarSolar.AspNetCore.Identity.PwnedPasswords
This library provides an [IPasswordValidator<TUser>](https://docs.microsoft.com/en-gb/dotnet/api/Microsoft.AspNetCore.Identity.IPasswordValidator-1?view=aspnetcore-2.0) for [Microsoft ASP.NET Core Identity](https://github.com/aspnet/Identity) which validates passwords against [HaveIBeenPwned.com](https://haveibeenpwned.com/)'s [Pwned Passwords](https://haveibeenpwned.com/Passwords) using the v2 RESTful API.
## Usage
To use the default error message:
```c#
public class Startup
{
     public void ConfigureServices(IServiceCollection services)
     {
        services.AddIdentity<MyApplicationUser, IdentityRole>()
            .AddPwnedPasswordsValidator<MyApplicationUser>();
     }
}
```
To specify a custom error message for pwned password:
```c#
public class Startup
{
     public void ConfigureServices(IServiceCollection services)
     {
        services.AddIdentity<MyApplicationUser, IdentityRole>()
            .AddPwnedPasswordsValidator<MyApplicationUser>(options => options.ErrorMessage = "Custom error message");
     }
}
```