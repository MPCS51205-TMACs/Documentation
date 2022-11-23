# EVENTS
## USER
### USER.CREATE  
Body: `User`   
Exchange Type: `fanout`  
Publishers: `user-service`  
### USER.UPDATE
Body:  
```  
{
userId: UUID   
user: User  
}  
```  
Exchange Type: `fanout`  
Publishers: `user-service`  
### USER.DELETE
Body:  
```  
{
userId: UUID    
}  
```  
Exchange Type: `fanout`  
Publishers: `user-service` 


## AUCTION
### AUCTION.START

Body:  
```  
{
sendTo: 'seller' or 'bidder'
userId: UUID
itemId: UUID
timeToStart: String
}  
```  
Exchange Type: `fanout`  
Publishers: `auction-service` 

### AUCTION.END
Body:  
```  
{
sendTo: "seller" or "bidder"
userId: UUID
itemId: UUID
auction: Auction
}  
```  
Exchange Type: `fanout`  
Publishers: `auction-service` 

### AUCTION.NEW-HIGH-BID
Body:  
```  
{
sendTo: "seller" or "bidder"
userId: UUID
itemId: UUID
oldBid: Bid
newBid: Bid
}  
```  
Exchange Type: `fanout`  
Publishers: `auction-service` 

### AUCTION.HIGH-BID-INACTIVE
Body:  
```  
{
sendTo: "seller" or "bidder"
userId: UUID   
inactiveBid: Bid
item: Item
}  
```  
Exchange Type: `fanout`  
Publishers: `auction-service` 


## WATCHLIST
### WATCHLIST.MATCH
Body:  
```  
{
userId: UUID
itemId: UUID   
}  
```  
Exchange Type: `fanout`  
Publishers: `watchlist-service` 

## ITEM
### ITEM.COUNTERFEIT
### ITEM.INAPPROPRIATE
### ITEM.CHANGE


