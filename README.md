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
  "customer_id" INT REFERENCES "Users"("user_id")
	CONSTRAINT "Product_pk" PRIMARY KEY ("product_id")
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


- File Structure:
  - Server/
    - index.js
    - controllers/
      - authController.js
      - productsController.js
      - CartController.js


## FRONTEND
-Dependencies 
  -React
  -React-Redux
  -React-Router
  -Redux
  -Redux-middleware
  -Material UI
  -Axios


- File Structure 
  - src/
  - Files that comes with creat-react-app
  - routes.js
  - componenets/
    - Cart.js
    - Main.js
    - Products.js
    - Header.js
    - Auth.js
    - Footer.js
  -Redux
    -reducer
    -store



  


