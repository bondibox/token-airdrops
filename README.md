Written by @colradi for Community Node Super Representative Organization 
Contact us on Telegram for scripting services t.me/CommunityNode
GUI Interface coming soon!

This is a script for airdropping tokens (not TRX) based on votes for Super Representative.

The ratio of tokens to votes can be configured with the multiplier variable

There are two files that work together, generateFile.js and tron\_air.js

generateFile.js will set the SR Candidate whose voters you will be rewarding
generateFile.js will set the AMOUNT of tokens you will be rewarding per-vote
generateFile.js will fetch an array of voters along with the amount of tokens to be airdropped to each.

The amount of tokens per voter is their number of votes, times the 'multiplier'
This script output will name a new file in the format  

>  votes\_ADDRprefix\_DATE\_at\_TIME.json

It will contain an array like this:

	
> { "list":  [  
> 		{"address" : "TXBnjY7CAq39Jj748XLfLd97tXGyknwD1x" , "votes" : 2004538},  
> 		{"address" : "TQ5qpcvtruNdYwokc3JHGb6dzuYMbam485" , "votes" : 1788121},  
> 		{"address" : "TUvV7VFJuj4wcd2ny3ZT3rZXivGpmhWoDV" , "votes" : 1473256},  
> 		{"address" : "TAh4zm9ULixhuCauikkaBjNCgnDptX5bW5" , "votes" : 1  }    
> 		]  
> }


Your command line output will give you the exact command to call for your specific filename
The airdrop runs with the tron\_air.js script.

tron\_air.js is where you set the token ID for the airdrop
tron\_air.js is where you set the wallet sending the airdrop 
tron\_air.js is where you set the private key for the wallet sending the airdrop.

Do NOT enter the actual value for the private key!  
Private key for wallet defined in 'air_address' has to be stored as an environment var  
$AIRDROP\_PK  

'air_address' Defines sender's wallet address, good idea to store as an environment var  
$AIRDROP\_ADDR  


************************ Command line  USAGE    *******************************


begin with creating a project directory  
    `mkdir my\_token\_airdrop`
    `cd my\_token\_airdrop`
    `npm init`

now install NPM Libraries  
    `npm install tronvotes`  
    `npm install tronix.js`

Run the first script  
    `node generateFile.js`

Check the output versus data from tronscan. If all looks ok, then proceed with the airdrop:

    `node votes\_ADDRprefix\_DATE\_at\_TIME.json`  (the exact command will be provided by generateFile.js output)

Remember you must have sufficient bandwidth or TRX balance to conduct an airdrop.




########################### transaction object example: ########################### 

/*
{ result: true,
  code: 0,
  message: '',
  transaction:
   { assetName: '1000322',
     ownerAddress: 'TNtPJVFFGWYRYXUaa1XJhW6MCoNQzW1nkk',
     toAddress: 'TXBnjY7CAq39Jj748XLfLd97tXGyknwD1x',
     amount: 1,
     contractType: 2,
     hash: 'a77cadb2722d7489ae9f5007fc88c41fe4fe9cef0de48d01ad684b1144cafb29',
     time: 1549896394610,
     data: '' } }

*/



