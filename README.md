# Asp .Net Core Authentication And Authorization

* Authentication and Authorization takes very important role in all the applications. Action views or pages should be enabled based on roles.

* We can implement authentication and authorization in many ways, but in this article we will implement the same in very simple manner.

* Cookie Authentication  is the One of the easiest methods to implement your own Custom Authentication Logic in ASP.NET Core.

* We should keep in mind that it is not related to any ASP.NET Core Identity, it is the own way to implement the A & A.

## Lets start implementing it.

* Open Visual Studio and Create ASP.Net Core Web App Model-View-Controller

![image](https://user-images.githubusercontent.com/81896060/121781468-8d523100-cbc2-11eb-8bb2-8a5eb2934b8f.png)

* Call it **MyAuthenticationAndAuthorization**

![image](https://user-images.githubusercontent.com/81896060/121781504-b70b5800-cbc2-11eb-9cf1-39d88a1ff718.png)

* Next select **.Net Core 3.1(LTS)**

	Authentication : **None**
  
	Check **Enable Razor runtime-compilation**
  
  ![image](https://user-images.githubusercontent.com/81896060/121781544-efab3180-cbc2-11eb-86b6-69292952afa3.png)

* Go to nuget package and add the below mentioned package

    **Microsoft.AspNetcore.Authentication**

![image](https://user-images.githubusercontent.com/81896060/121781581-0d789680-cbc3-11eb-9c96-77b2bad739e5.png)

* Go to Startup.cs add the below lines under **Configure()** method
 	     
```
 app.UseAuthentication();
 app.UseAuthorization();
```

![image](https://user-images.githubusercontent.com/81896060/121781694-a9a29d80-cbc3-11eb-8c35-0e1b53609ce1.png)

Also add the below code in ConfigureServices(IServiceCollection services)

```
 services.AddAuthentication(CookieAuthenticationDefaults.AuthenticationScheme).
                AddCookie(o => o.LoginPath = new Microsoft.AspNetCore.Http.PathString("/account/login"));
```

![image](https://user-images.githubusercontent.com/81896060/121782050-5cbfc680-cbc5-11eb-85f5-741855ed0b4b.png)


