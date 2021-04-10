1. Pull SQL container image:
    ```
    sudo docker pull mcr.microsoft.com/mssql/server:2019-latest
    ```
2. Run image

    *Container will **<span style="color:yellow">raise error when use command</span>** if the password don't at least 8 characters long with Uppercase letters, Lowercase letters, Base 10 digits, and Symbols.
   ```
   sudo docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=<YourStrong@Passw0rd>" \
   -p 1433:1433 --name sql1 -h sql1 \
   -d mcr.microsoft.com/mssql/server:2019-latest
   ```
3. Connect locally with sqlcmd
  
   * Run sql command in container
    ```
    sudo docker exec -it sql1 "bash"
    ```
   * Connect locally 
    ```
    /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P "<YourNewStrong@Passw0rd>"
    ```
   * If successful, you should get to a sqlcmd command prompt: ```>1```