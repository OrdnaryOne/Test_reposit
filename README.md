
Create Table transaction (
  transaction_id integer not null primary key
  , product_id integer not null
  , customer_id integer not null
  , transaction_date timestamp not null
  , online_order bool not null
  , order_status varchar not null
)

Create Table product (
  product_id integer not null
  , brand varchar not null
  , product_line varchar not null
  , product_class varchar not null
  , product_size varchar not null
  , list_price float not null
  , standard_cost float not null
  , unique (product_id, brand)
)

Create Table customer (
  customer_id integer primary key
  , first_name varchar not null
  , last_name varchar
  , gender varchar not null
  , DOB timestamp not null
  , job_title varchar
  , job_industry_category varchar not null
  , wealth_segment varchar not null
  , deceased_indicator varchar not null
  , owns_car bool not null
  , address_id integer not null
)

Create Table address (
  address_id integer not null primary key
  , address varchar not null
  , postcode integer not null
  , state varchar not null
  , country varchar not null
  , property_valuation integer not null
)

truncate customer
delete address

insert into transaction
values('1','2','2950','2017-02-25','False','Approved')
, ('2','3','3120','2017-05-21','True','Approved')
, ('3','37','402','2017-10-16','False','Approved')
, ('4','88','3135','2017-08-31','False','Approved')
, ('5','78','787','2017-10-01','True','Approved')
select *
from transaction

insert into product
values('2','Solex','Standard','medium','medium','71.49','53.62')
, ('3','Trek Bicycles','Standard','medium','large','2091.47','388.92')
, ('37','OHM Cycles','Standard','low','medium','1793.43','248.82')
, ('88','Norco Bicycles','Standard','medium','medium','1198.46','381.1')
, ('78','Giant Bicycles','Standard','medium','large','1765.3','709.48')
select *
from product

insert into customer
values('1', 'Laraine', 'Medendorp', 'F', '1953-10-12', 'Executive Secretary', 'Health', 'Mass Customer', 'N', 'Yes', '1')
, ('2', 'Eli', 'Bockman', 'Male', '1980-12-16', 'Administrative Officer', 'Financial Services', 'Mass Customer', 'N', 'Yes', '2')
, ('3', 'Arlin', 'Dearle', 'Male', '1954-01-20', 'Recruiting Manager', 'Property', 'Mass Customer', 'N', 'Yes', '3')
, ('4', 'Talbot', '', 'Male', '1961-10-03', '', 'IT', 'Mass Customer', 'N', 'No', '4')
, ('5', 'Sheila-kathryn', 'Calton', 'Female', '1977-05-13', 'Senior Editor', 'n/a', 'Affluent Customer', 'N', 'Yes', '5')
select *
from customer

insert into address
values('1','060 Morning Avenue','2016','New South Wales','Australia','10')
, ('2','6 Meadow Vale Court','2153','New South Wales','Australia','10')
, ('3','0 Holy Cross Court','4211','QLD','Australia','9')
, ('4','17979 Del Mar Point','2448','New South Wales','Australia','4')
, ('5','9 Oakridge Court','3216','VIC','Australia','9')
select *
from address
