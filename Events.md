# EVENTS
## USER
### USER.CREATE  
Body: `User`   
Exchange Type: `fanout`  
Publishers: `user-service`  
### USER.UPDATE
Body:  
```{
userId: UUID   
user: User  
}  
```  
Exchange Type: `fanout`  
Publishers: `user-service`  
