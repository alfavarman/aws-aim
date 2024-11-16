1) add permissions from json file RDSLimmitedAccess
2) create group DBAdmins, add this permissions to this group
3) create user and add him to above group and add him tag Department=DBAdmins
4) create 2 dbs (anykind) add to each tag: Environment=Production and for another Environment=Development
5) log as Wojtek and see you can 'play' (restart db) but got permissions error with develpment
6) modifi permission:
7) "rds:db-tag/Environment": "Production" => "rds:db-tag/Environment": ["Production", "Development"]
8) and check you can play with both...
9) attempt to remove db, from error get a permission required and update permissions.
10) remove one db instance without adding snapshot permissions!