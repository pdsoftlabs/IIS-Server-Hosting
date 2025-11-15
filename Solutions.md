Dont over complicate things.

## APIs hosting made simple

1. Install IIS server with settings (get help from Chatgpt)
2. Download hosting bundle (matching .net version)
3. publish the api project first at a random location initially (C:Deploy/api)
4. Create Images Folder immediately
5. go to web.config -> set this variable to true -> stdoutLogEnabled="true"
6. move this entire folder to C:inetpub/wwwroot/restapis (restapis is the newly create folder structure)
7. next, go to iis -> add a site first -> select port no. 5000 -> save
8. now apis will get launched on http://localhost:5000/swagger
9. but db issue remains -> to resolve this issue follow no.9
10. go to W + R -> `eventvwr` -> windows logs -> Application -> check the latest `Information` or `Error` or `Warning` log
11. something like this -> Login failed for user 'IIS APPPOOL\DotnetApi'. Reason: Failed to open the explicitly specified database 'InventoryPro'. [CLIENT: <local machine>]
12. then go to database (sql server via ssms) -> security -> Logins -> right click -> Enter login name (IIS APPPOOL\DotnetApi) -> Ok
13. then go to that particular login -> IIS APPPOOL\DotnetApi -> right click -> Properties -> User mapping -> select the database for which you want to allow permissions -> allow next set of permissions -> db_datareader and db_datawriter -> Ok
14. Done. Apis are live now with active db support/connection. 

## UI hosting

1. Most of the things are already set
2. publish the project at random location
3. go to web.config -> set this variable to true -> stdoutLogEnabled="true"
4. move all files to inetpub/wwwroot/ui (create new folder called 'ui')
5. Almost done.
