- ### Configure
Create a liquibase.properties
```
        # for testing and poc used the sqlite3 db engine
        url: jdbc:sqlite:db/db/liq_poc.db
        #changelogFile: changeLog.xml
        changelogFile: master-changelog.xml
        username: test
        password: test
```
Capture state and create changelog
```shell
	liquibase generate-changelog --changelog-file=dbchangelog.xml 
```
Verify the SQL

```shell 
    # as per the properties file 
    liquibase update

    # as custom chnageLogfile
    liquibase update-sql --changelog-file=changelog\release-1.0.2.xml
```
Apply the package
```shell 
    # as per the properties file
    liquibase update

    #custom
    liquibase update --changelog-file=changelog\release-1.0.2.xml
```
	-
	-