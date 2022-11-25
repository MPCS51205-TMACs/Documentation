# EVENTS
## USER
### user.create  
Body: `User`   
Exchange Type: `fanout`  
Publishers: `user-service`  
### user.update
Body:  
```  
{
userId: UUID   
user: User  
}  
```  
Exchange Type: `fanout`  
Publishers: `user-service`  
### user.delete
Body:  
```  
{
userId: UUID    
}  
```  
Exchange Type: `fanout`  
Publishers: `user-service` 


## AUCTION
### auction.start

Body:  
```  
{
auction: Auction
timeToStart: String
}  
```  
Exchange Type: `direct`  
Publishers: `auction-service` 

### auction.end
Body:  
```  
{
auction: Auction
}  
```  
Exchange Type: `fanout`  
Publishers: `auction-service` 

### auction.new-high-bid
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
Exchange Type: `direct`  
Publishers: `auction-service` 

### auction.high-bid-inactive
Body:  
```  
{
sendTo: "seller" or "bidder"
userId: UUID   
inactiveBid: Bid
item: Item
}  
```  
Exchange Type: `direct`  
Publishers: `auction-service` 


## WATCHLIST
### watchlist.match
Body:  
```  
{
userId: UUID
itemId: UUID   
}  
```  
Exchange Type: `direct`  
Publishers: `watchlist-service` 

## ITEM
### item.create
Body: `Item`
Exchange Type: `direct`
Publishers: `item-service`

### item.update
Body:
```
{
itemId: UUID
update: Item
}
```


