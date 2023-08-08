---
creation date: August 7th 2023
last modified date: August 7th 2023
aliases: []
tags: #🧩
---

Search Tag: #🧩  

# [[CS - L3C3 Intern Base - Off Balance]]  
___

## Briefing

>We're hot on the heels of catching this cyber gang but the closer we get, the more damage they try to inflict onto the Barcelona tourism industry!
>This time, they've hacked into a large international bank's mobile application. Customers of the bank are complaining they can't see their current **balance** and these criminal masterminds need to be held to **account**. Intern, help customers retrieve their balances, so they can continue to spend their money during their well-earned holidays!
>Helping our international friends will really help develop our **network**.


![[Pasted image 20230807204015.png]]

> If we open our dev tools (I like to just right click and hit inspect) and move to the `Network` tab after clicking through this IPhone we find that `get-balances` is coming up `404` while the others are coming in `200`

![[Pasted image 20230807204418.png]]

> Now if we pull up the details of the `get-balances` we can see this in greater detail, most importantly the URL request. 

![[Pasted image 20230807204503.png]]

> Lets see what a working request looks like...

![[Pasted image 20230807204621.png]]

> And if we visit this status `200` site we are greeted with an error...

![[Pasted image 20230807204718.png]]

> Easy enough, lets check the next tab to the `header`, `payload` and we find our token!

![[Pasted image 20230807204821.png]]

> Okay so we've done some digging...
> - We know the `get-balances` url is not working
> - We know the others are...
> - But we need a token to view the site while not in the app/IPhone
> - We have this token

> Lets swing by our terminal and use the tool `curl`












___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 7th 2023 (08:49 pm) 
Last Modified Date: August 7th 2023 (08:49 pm)
