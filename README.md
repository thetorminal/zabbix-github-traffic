# Zabbix Github Repository Traffic Monitoring
Monitoring of the traffic on your github repository with Zabbix.  

## Description
Based on the official Github Template from Zabbix: [Zabbix Template - Github](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/templates/app/github_http?at=release/7.2)  

Shows amount of traffic on your github repository. View the Dashboard in the template to get an overview over:  
* Stargazers
* Watchers
* Unqiue and all views
* Unique and all clones

Example Dashboard:  
![github-traffic](https://github.com/user-attachments/assets/0c33d875-0333-4749-9b53-7bc53bc83c55)

Tested with:  
* Zabbix Server 7.0.5
* Github API 2022-11-28

## Getting Started

### Dependencies
* Github with an access token 
* Zabbix Server

### Installing

#### Github:
* Get an access token for your Github account [Github Access Tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

#### On Zabbix frontend server:  
- download and import the template `github-repository-traffic.yaml`
- create a new host (named like your repo), add the template `Github repository traffic` to the host and add Interface "Agent" (127.0.0.1:10050)  

Add following MACROS to the new host: 
- {$GITHUB.API.TOKEN} = your API Token
- {$GITHUB.REPO.NAME} = name of your repo you want to monitor
- {$GITHUB.REPO.OWNER} = name of owner of repo

Now you can view the traffic on your github repository. Use the dashboard from the template, or add the items to your own dashboard!  

## Informations
API Reference "REST API endpoints for repository traffic":
* [Github API - Traffic](https://docs.github.com/en/rest/metrics/traffic?apiVersion=2022-11-28) 

## Version History
* 0.1
    * Initial Release

## Acknowledgments
* [Zabbix Template - Github](https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/templates/app/github_http?at=release/7.2) 
* [Github API - Traffic](https://docs.github.com/en/rest/metrics/traffic?apiVersion=2022-11-28) 
