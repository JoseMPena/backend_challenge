# Backend coding challenge

## Instructions
* Please read the challenge carefully and if you have any doubt or need extra information, please don't hesitate to ask us before starting.
* Design, test, develop and document the code. It should be a performant, clean and well structured solution.
* You should consider this code ready for production as if it were a PR to be reviewed by a colleague. Also use Git commits the same way as you would in your everyday work.
* You don't need to finish. We value quality over feature-completeness. If you have to leave things aside you can mention them on the README, explaining why and how you would resolve them.
* Please write a few lines to describe your solution, especially what assumptions you made.
* Also come up with questions that you would ask if this wasn't an exercise but a real world application. 
* Remember you're dealing with money, so you should be careful with related operations.
* Your level of experience will be taken into consideration when evaluating.
* Submit your solution as a private repository, giving us access so we can evaluate.

## Context
An ecommerce platform provides shops (merchants) a flexible payment method so their customers (shoppers) can purchase and receive goods. 
This platform collects the money from the shoppers and pays out (disburses) the merchant once the order is marked as completed.
The platform earns a small fee per purchase, which is subtracted from the collected money.

* Disbursements are done weekly on Monday.
* We disburse only orders which status is completed.
* The disbursed amount has the following fee per order:
  * 1.00 % for amounts smaller than 50 €
  * 0.95 % for amounts between 50 - 300 €
  * 0.85 % for amounts over 300 €

## The task
The operations manager asked you to make a system to calculate how much money should be disbursed to each merchant.

* Build an API endpoint that exposes the disbursement for a given merchant on a given week. If no merchant is provided, return for all of them.
* Create the necessary data structures and a way to persist and query the provided data. You don't have to follow our schema if you think another one suits better.
* The calculations should be isolated so they can easily be performed independent from a web request, for instance on the command line or in a background job.

Find the merchants, shoppers and orders data in the `backend challenge dataset` folder. You can use either the JSON or CSV files, whatever is easier for you. 
The data is structured as follows:

### MERCHANTS

```
ID | NAME                      | EMAIL                             | CIF
1  | Treutel, Schumm and Fadel | info@treutel-schumm-and-fadel.com | B611111111
2  | Windler and Sons          | info@windler-and-sons.com         | B611111112
3  | Mraz and Sons             | info@mraz-and-sons.com            | B611111113
4  | Cummerata LLC             | info@cummerata-llc.com            | B611111114
```

### SHOPPERS

```
ID | NAME                 | EMAIL                              | NIF
1  | Olive Thompson       | olive.thompson@not-gmail.com       | 411111111Z
2  | Virgen Anderson      | virgen.anderson@not-gmail.com      | 411111112Z
3  | Reagan Auer          | reagan.auer@not-gmail.com          | 411111113Z
4  | Shanelle Satterfield | shanelle.satterfield@not-gmail.com | 411111114Z
```

### ORDERS

```
ID | MERCHANT ID | SHOPPER ID | AMOUNT | CREATED AT           | COMPLETED AT
1  | 25          | 3351       | 61.74  | 2017-01-01 00:00:00  | 2017-01-07 14:24:01
2  | 13          | 2090       | 293.08 | 2017-01-01 12:00:00  | nil
3  | 18          | 2980       | 373.33 | 2017-01-01 16:00:00  | nil
4  | 10          | 3545       | 60.48  | 2017-01-01 18:00:00  | 2017-01-08 15:51:26
5  | 8           | 1683       | 213.97 | 2017-01-01 19:12:00  | 2017-01-08 14:12:43
```

**HAPPY CODING!!**
