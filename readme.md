
##Explorer Mode
##### How many users are there?
50
```
SELECT COUNT(*) FROM users;
```

##### What are the 5 most expensive items?
Small Cotton Gloves
Small Wooden Computer
Awesome Granite Pants
Sleek Wooden Hat
Ergonomic Steel Car
```
SELECT title FROM items ORDER BY price DESC LIMIT 5;
```

##### What's the cheapest book? (Does that change for "category is exactly 'book'" versus "category contains 'book'"?)
Ergonomic Granite Chair
```
SELECT title FROM items WHERE category IS "Books" ORDER BY price ASC LIMIT 1;
```

##### Who lives at "6439 Zetta Hills, Willmouth, WY"? Do they have another address?
Kyra Kilback, no other address
```
SELECT first_name, last_name FROM addresses JOIN users ON addresses.id = users.id WHERE street IS "6439 Zetta Hills";
```

##### Correct Virginie Mitchell's address to "New York, NY, 10108".

```
UPDATE addresses SET city = "New York", state = "NY", zip = "10108" WHERE id IS (SELECT id FROM users WHERE first_name = "Virginie");
```

##### How much would it cost to buy one of each tool?
46477
```
SELECT SUM(price) FROM items WHERE category LIKE "%Tools%";
```

##### How many total items did we sell?
2125
```
SELECT SUM(quantity) FROM orders;
```

##### How much was spent on books?

##### Simulate buying an item by inserting a User for yourself and an Order for that User.


##Adventurer Mode
##### What item was ordered most often? Grossed the most money?

##### What user spent the most?

##### What were the top 3 highest grossing categories?
