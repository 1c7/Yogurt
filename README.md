# Milk - a extremely simple "License Management tool" that use Serverless     
Genereate & Verify License code, that's all.  
(License code like 111111-222222-333333)

## It's for 
* Sell Desktop app
* **One-off purchase**
* License code generate & verify API (total of 2 API endpoint)

## It's not for
* Web SaaS app that charge $x/month (recurring payment)

## If you can use Gumroad or Paddle. you don't need this.  
Gumroad have all these license genereate tool, very convenient.  
Paddle is the same.  
This is for payment provider that doesn't support "license code generate and verify"   

## Tech Stack
* serverless.com
* AWS 

## Usage Scenario (very niche)
1. You have a Desktop app (maybe written in Electon.js)
2. You want charge money for that software
3. It's One-off purchase($9 forever), not monthly recurring payment($15 per month).
4. You don't want spend a lot of time(2-7 days maybe) thinking and building a license management system

## Why this
1. Simple   
  ("Simple" in some way, if you are new to serverless, there are still new concept you need to know)
2. Cheap   
  (Cheaper than a dedicate server that run 24x7 (I don't even want pay for a $5 dollar Digital Ocean Droplet, Problem is not the money, I just don't want maintain it)

## How it work (user flow)
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

## Further more
If people trying to abuse this, share their "Email + License code" combination online for free.  
and you saw it, you can just delete that line. so now that's invalid.  

## Conclusion
In it's core, it just a really simple CURD serverless app    

## How to use this.  
(fill this)  

## Alternative
* https://snipeitapp.com/
* https://www.pfind.com/alternatives/gumroad
* https://selz.com (14 day Free Trial, then $29/mo)
* https://sellfy.com (14 day Free Trial, then $29/mo)
* Gumroad
* Paddle
* https://payhip.com
* https://www.e-junkie.com/

## Why build this
1. I can't use Paddle or Gumroad
  (well, not exactly "can't use", I use Gumroad for people in the U.S. EU, western world in general (have credit card), And I need to use Xorpay for China market)

2. I want something **Simple** (I don't want deal with existig solution that use C++ or Java or need to deploy to server with a over complicated Web UI)

3. I want something **Cheap**


## License
MIT