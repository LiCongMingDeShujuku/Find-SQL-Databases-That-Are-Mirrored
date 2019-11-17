![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 查找镜像的（mirrored）SQL数据库
#### Find SQL Databases That Are Mirrored
**发布-日期: 2015年5月28日 (评论)**



## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
这是一些用于获取当前在服务器上镜像的（mirrored）数据库列表的快速SQL逻辑（logic）。它还显示每个数据库的镜像状态，包括当前服务器（运行脚本的位置）的角色，例如是否是Principal或是包括作为镜像服务器的辅助服务器名称以及镜像端口的Mirror。


## English
Here’s some quick SQL logic to get a list of databases that are currently being mirrored on your server. It also shows the mirror state of each database including the current server (where you running the script) role as to if it’s the Principal or the Mirror including the secondary server name which is the mirror server plus the port being used for the mirror.

---
## Logic
```SQL
se master;
set nocount on

select
	'database name' 		= DB_NAME(database_id)
, 	'mirror state' 			= mirroring_state_desc
, 	'current mirror role' 	= mirroring_role_desc
, 	'partner server name' 	= mirroring_partner_name
from
	sys.database_mirroring
where
	mirroring_guid is not null


```

![#](images/find-sql-databases-that-are-mirrored.png?raw=true "#")

[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

