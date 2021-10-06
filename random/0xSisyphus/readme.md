# Bounty for 0xSisyphus
https://twitter.com/0xSisyphus/status/1445378356619382786?s=20  
![image](https://user-images.githubusercontent.com/9086733/136124795-97c1e765-2b4f-4557-ae2c-192293f1922b.png)  
## TL:DR
Raw Data Here
[OpenSeaData-0xSisyphus.csv](https://github.com/antonyip/aave_dashboards/files/7290121/OpenSeaData-0xSisyphus.csv)

## Query Used 
```
select sum(price_usd) as usd_volume, 
  sum(price) as eth_volume,
  date_trunc('day',block_timestamp) as date,
  coalesce(project_name,'unlabeled') as project_name
  from ethereum.nft_events 
  where event_platform = 'opensea' 
  and price_usd < 100000000
  and tx_currency in ('ETH','WETH')
  and block_timestamp > '2021-09-15' 
group by 3,4;
```
## Plug for FlipsideCrypto
You can write your own SQL queries and query the ethereum blockchain @ [https://app.flipsidecrypto.com/velocity](https://app.flipsidecrypto.com/velocity)  
It has API endpoints which you can use to pull the data like [here](https://api.flipsidecrypto.com/api/v2/queries/397d754a-5f73-4071-bcb5-ad5439dea98d/data/latest)!  
Try it out today!
