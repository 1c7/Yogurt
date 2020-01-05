# Serverless License Management
Here is a simple license management run on Serverless.    
I built this for my desktop app    

### If you can use Gumroad or Paddle. you don't need this.  
Gumroad have all these license genereate tool, really convenience. 
Paddle, the same.  
This is for payment provider that doesn't support "license code generate and verify"   

### Usage Scenario (very niche)
1. You have a Desktop app (maybe written in Electon.js)
2. You want charge money for that software
3. It's One-off purchase($9 forever), not monthly recurring payment($15 per month).
4. You don't want spend a lot of time(2-7 days maybe) thinking and building a license management system

In that case, this tool may be useful for you. 

### How it work
1. When user want purchase your one-off software, ask user for Email address (so user can receive license code via email)
2. User pay & successfully pay
3. That payment provider probably have webhook when payment success. use that. call this "Serverless License Management"
4. serverless code would verify the requests indeed come from payment provider (maybe calculate Sign)
5. generate license code, insert "Email" and "License code" into DynamoDB.
6. email the license code to user
7. done.
8. When user want to active your software, they input 2 things
9. Email + License code, it kinda like "username" and "password"
10. Your Desktop app send request to this "Serverless License Management", if this combination of "Email + License code" exists. this License is valid!

### Further more
If some people trying to abuse this, share their "Email + License code" combination online for free.  
and you saw it, you can just delete that line. so now that's invalid.  

### Conclusion
There may seem like a lot of text but in it's core a really simple CURD app.  

### How to use this.  