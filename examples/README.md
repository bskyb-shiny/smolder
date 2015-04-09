Examples
========

Here are some contrived examples that you can run.  


*github_status.json* 
- connects to status.github.com on port 80 and expects to be redirected to https://status.github.com/ with a 301.  
- then tests https://status.github.com/ and FAILs if github is reporting issues on their status page.  
- Expect the final test of site speed to fail as 200ms is typically about half the normal page load time for https://status.github.com.

```
smolder-cli status.github.com github_status.json
```

*aws_status.json*
- another contrived status page example

```
smolder-cli status.aws.amazon.com aws_status.json
```

*example_test.json*
- tests an RFC1918 (won't work out of the box) address by trying to PUT data to it and verifying the result. 

```
smolder-cli 10.0.0.1 example_test.json --force
```


*soa_test.json*
- tests an https endpoint which has an issue with it's certificate
```
smolder-cli 173.223.194.219 soa_test.json
```