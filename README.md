# FlopX
<hr/>



## MVP
- Users can create an account
- users can login
- users can put orders into the cart
- users can checkout orders
- users can delete items from the cart
- users can view all items in the store


## ICEBOX
- users can get order delivered 
- users can see purchase history
- users can review product

## DB
```SQL
CREATE TABLE "Users" (
	"user_id" SERIAL PRIMARY KEY,
	"email" VARCHAR(50) NOT NULL,
	"username" VARCHAR(25) NOT NULL,
	"password" VARCHAR(500) NOT NULL,
	"isActive" BOOLEAN NOT NULL,
	CONSTRAINT "Users_pk" PRIMARY KEY ("user_id")
) WITH (
  OIDS=FALSE
);



CREATE TABLE "Product" (
	"product_id" SERIAL PRIMARY KEY,
	"product_name" VARCHAR(25) NOT NULL,
	"product_price" serial NOT NULL,
	"stock_amount" INT NOT NULL,
	"in_stock" BOOLEAN NOT NULL,
	CONSTRAINT "Product_pk" PRIMARY KEY ("product_id")
) WITH (
  OIDS=FALSE
);



CREATE TABLE "Purchases" (
	"customer_id" SERIAL PRIMARY KEY,
	"product_name" VARCHAR(25) NOT NULL,
	"product_id" serial NOT NULL,
	"amount" INT NOT NULL,
	CONSTRAINT "Purchases_pk" PRIMARY KEY ("customer_id")
) WITH (
  OIDS=FALSE
);



CREATE TABLE "Cart" (
	"cart_id" SERIAL PRIMARY KEY NOT NULL,
	"isActive" BOOLEAN NOT NULL,
	"exp_on" DATE NOT NULL,
	CONSTRAINT "Cart_pk" PRIMARY KEY ("cart_id")
) WITH (
  OIDS=FALSE
);


```

## SERVER 


- Dependencies: 
  - massive
  - -express
  - express-session
  - bcrypt
  - dotenv

- register `auth/register`
- login   
- logout
- getOrder
- editOrder
- deleteOrder



## FRONTEND
