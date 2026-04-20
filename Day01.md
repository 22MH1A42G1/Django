# day 01
## Django (web framework)
```
1. sample side laguage
2. framework 
--
machine 
sample.py {---}
          {---} python sample.py
--
 client-browser    server-browser       laptop/pc
   |------|    -->   |-------|    -->   | django  |
   |------|          |-------|           ---------
  javascript                                ||
                        |                         |
                        | installed python 11     |
client1---> project 01->| django 3.2              |
                        | mysql                   |
                        |                         |

client2---> project 02->| python 12               |
                        | django 3.6              |
                        | oracel                  |
                        | aws                     |
client3---> project 03->| python 14               |
                        | django 5.0              |
                        | postgresql              |
                        | aws                     |
                        | azure                   |
                          developer machine       |

--------------------------------------------------------------
             venv
            --------------
           | python 3.11 |
           | django 3.2  | -----------------> clent-01 project1
           | mysql       |


           ---------------
           | python 3.13 |
           | django 4.0  | -----------------> clent-02 project2
           | mysql       |
------------------------------------------------------------------
laptop/ pc

```

### create create virtual environment
```
pip venv venv # for cmd
conda create --name env1 python==3.13 # for anaconda base path , it can be /c:/username/FolderName
conda activate env1
```

## installing django
```
pip install django-admin===4.1
```

## steps creating project
1. create environment with python and django
2. activate environment
3. go to the location where you want to create your project
4. create project using environment
5. cd projet_name
6. start projet with python manage.py runserver
7. get the project url and access project inside browser
