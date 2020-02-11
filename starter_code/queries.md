![Ironhack Logo](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Answers

### 1. All the companies whose name match 'Babelgum'. Retrieve only their `name` field.

<!-- Your Code Goes Here -->

{
"name": "Babelgum"
}
//options
{
"project": {
"name": 1
}
}

### 2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.

<!-- Your Code Goes Here -->

{
"number_of_employees": {"\$gt": 5000}
}

//options

{
"limit": 20
}

### 3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fields.

<!-- Your Code Goes Here -->

{
$and: [{"founded_year": {"$gte": 2000}},
{"founded_year": {"\$lte": 2005}}]
}
{
name: 1,
founded_year:1
}

### 4. All the companies that had a Valuation Amount of more than 100.000.000, and have been founded before 2010. Retrieve only the `name` and `ipo` fields.

<!-- Your Code Goes Here -->

{$and:[{"ipo.valuation": {$gt:100000000}}, {founded_year: {\$lt: 2010}} ] }

{
name:1,
ipo:1
}

### 5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.

<!-- Your Code Goes Here -->

{$and: [{number_of_employees: {"$lte": 1000}}, {founded_year: {"\$lte": 2005}} ]}

//options

{number_of_employees: 1}

limit: 10

### 6. All the companies that don't include the `partners` field.

<!-- Your Code Goes Here -->

{"partners": {\$exists: false}}

### 7. All the companies that have a null value on the `category_code` field.

<!-- Your Code Goes Here -->

{"category_code": {\$type: 10}}

### 8. All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.

<!-- Your Code Goes Here -->

{$and: [{"number_of_employees": {$gt:100}}, {"number_of_employees": {\$lt: 1000}}]}

//options

{name:1, number_of_employees: 1}

### 9. All the companies ordered by their IPO price in a descending manner.

<!-- Your Code Goes Here -->

not done

### 10. The 10 companies with the highest amount of employees, order by the `number of employees`.

<!-- Your Code Goes Here -->

//options

{"number_of_employees": -1}

limit: 10

### 11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.

<!-- Your Code Goes Here -->

{"founded_month": {\$in: [6, 7, 8, 9, 10, 11, 12]}}

//options

Limit: 1000

### 12. All the companies founded before 2000 that have an acquisition amount of more than 10.000.000.

<!-- Your Code Goes Here -->

{$and: [{"founded_year": {$lte: 2000}}, {"acquisition": {\$gte: 10000000}}] }

### 13. All the companies that have been acquired after 2010, ordered by the acquisition amount, retrieving only their `name` and `acquisition` fields.

<!-- Your Code Goes Here -->

{"acquisition.acquired_year": {\$gt: 2010}}

//options

{"name": 1, "founded_year": 1}

{"acquisition.price_amount": 1}

### 14. All companies ordered by their `founded year`, retrieving only their `name` and `founded year`.

<!-- Your Code Goes Here -->

{$and: [{"name": {$exists: true}}, {"founded_year": {\$exists: true}}]}

//options

{"name": 1, "founded_year": 1}

### 15. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `acquisition price` in a descending order. Limit the search to 10 documents.

<!-- Your Code Goes Here -->

{"founded_day": {\$in: [1, 2, 3, 4, 5, 6, 7]}}

//options

{"acquisition.price_amount": -1}

limit: 10

### 16. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascending order.

<!-- Your Code Goes Here -->

{$and: [{"category_code": "web"}], "number_of_employees": {$gt: 4000}}

//options

{"number_of_employees": 1}

### 17. All the companies whose acquisition amount was more than 10.000.000, and in which the acquisition currency is 'EUR'.

<!-- Your Code Goes Here -->

{$and: [{"acquisition.price_amount": {$gt: 10000000}}, {"acquisition.price_currency_code": {\$eq: "EUR"}}]}

### 18. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.

<!-- Your Code Goes Here -->

{"acquisition.acquired_month": {\$in:[1, 2, 3]}}

//options

{"name": 1, "acquisition": 1}

### 19. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.

<!-- Your Code Goes Here -->

{$and:[{founded_year: {$gt: 2000}}, {founded_year: {$lt: 2010}}, {"acquisition.acquired_year": {$gte: 2011}}]}
