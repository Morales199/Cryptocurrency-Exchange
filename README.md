# Cryptocurrency-Exchange
Analysis of the January Ledger of a Currency Exchange Company
 select * from transactions
 limit 3;

 --what is the total money in (users bought) in the table ? ANS:17173.0
 select sum(money_in) from transactions;

-- What is the total money out (users sold) in the table ? ANS:33417.0
select sum(money_out) from transactions;

-- how many money in transaccion are in this table? ANS: 43 
select count(money_in) from transactions;

--How many money_in transaction where BIT on this table: ANS: 21 
select COUNT(money_in) from transactions
where currency = 'BIT';

--what as the larget transaction in this table, money in or money out ? ANS: money out. 
select max(money_in) as 'max money in'from transactions; 

select max (money_out) as 'max money out' from transactions;

--what is the avg money in in the table for the currency eth ANS: $132
select round(avg(money_in)) as 'avg ETH money in'from transactions
where currency = 'ETH';

--Let built a ledger for the different dates 
select date, round(avg(money_in),2) as 'avg money in', round(avg(money_out),2) as 'avg money out' from transactions
group by 1;



