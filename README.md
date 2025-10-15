# Application the REST API in GoLang

That has at least the following entities (be able create, delete, update, list):

**user (username, email, ....)**  
* username can't be changed

**key (name, secret, username, ...)**
* one user can have multiply keys
* 'secret' should not be stored in DB but in Vault  
* key can be removed, can't be updated  

**item (sector, name, description, ...)**
* 'sector' and 'name' can't be changed
* in order to perform operations on 'item' the request should contain 'key'

system validates the key, check if user for which this key was generated has proper policy for operation and either allows it or denies    

**policy (name, definition, ...)**
* one policy can be assigned to multiply users
* policy defines what kind of operations given user can perform on 'items':

**As DB used PostgreSQL;**

The application (including DB) start and stopped using docker compose;
