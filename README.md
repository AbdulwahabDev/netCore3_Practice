# .netCore3_Practice

#  Section 2 L 17
initiate Angular libraryes using this command 
```
ng new DattingApp-SPA
```

use command ng serve to enable the Angluare to create hiding javascript and start the project ... 
```
DattingApp-SPA$ ng serve
```

create app componnet to build 4 main page for each app component and look for the app-tag 
and use it in HTML page ... 

1- click right in netCore3_Practice/DattingApp-SPA/src/app 
2- generate new commponent with what ever name you want ( it will create 4 files ... )

3- add [HttpClientModule] library in netCore3_Practice/DattingApp-SPA/src/app/app.module.ts
```
import {HttpClientModule} from '@angular/common/http';
```

4- clean main Anguler html and test new component <app-tag> 

# Section 2 L 13 

Async and await command  to avoid block all other connection while I have running one !! 

( in the Controller class )

1 - Add 'Async' after 'Public' and add 'Task<IActionResult> ' , add 'awite' in the first and  'Async' at the end for each call ! 
```
Public Async Task<IActionResult>  MethodName()
{ 
    - var result = await _context.Values.ToListAsync(); 
    - var result =  await _context.Values.FirstOrDefaultAsync( x => x.Id == id);  
}
```
 
# Section 2 L 12 

How to create link between source code and database using dotenoet entity framework 

1- Create Model for each taple to specify each column 

2- Create DataContext enherit from DbContext to create table And but it in ' Data ' folder
2-1- using Microsoft.EntityFrameworkCore;

3- Create constroctor 
```
 public DataContext(DbContextOptions<DataContext> options) : base(options){}
```

4- for each table I MUST create method return Dbset<ModelName> 

```
    public DbSet<Value> Values { get; set;} 
    // Values TableName
    // Value Model Contain all Values table column ... 
```

5- Create migrations using thist command 
```
dotnet ef migrations add
```
 6- Enable the migrations using this command 
 ```
 dotnet ef database update 
 ```
 