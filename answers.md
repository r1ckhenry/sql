    1. Selects the names of all products that are not on sale.

     select name from products where "on_sale" = "f";

    2. Selects the names of all products that cost less than £20.

    select name from products where "price" < 20;

    3. Selects the name and price of the most expensive product.

    select max(price), name from products;

    4. Selects the name and price of the second most expensive product.

    select max(price) from products where price < (select max(price) from products);

    5. Selects the name and price of the least expensive product.

    select min(price), name from products;

    6. Selects the names and prices of all products, ordered by price in descending order.

    select name, price from products order by price desc;

    7. Selects the average price of all products.

    select avg(price) from products;

    8. Selects the sum of the price of all products.

    select sum(price) from products;

    9. Selects the sum of the price of all products whose prices is less than £20.

    select sum(price) from products where price < 20;

    10. Selects the id of the user with your name.

    select id from users where name = 'YOUR NAME HERE';

    11. Selects the names of all users whose names start with the letter "J".

    select name from users where name like 'J%';

    12. Selects the number of users whose first names are "Spencer".

    select count(name) from users where name like 'Spencer%';

    13. Selects the number of users who want a "Teddy Bear".

    select count(product_id) from wishlists where product_id = 1;

    14. Selects the count of items on the wishlish of the user with your name.

    select count(product_id) from wishlists where user_id = 1;

    15. Selects the count and name of all products on the wishlist, ordered by count in descending order.

     SELECT products.name, COUNT(product_id) AS noitems FROM wishlists inner join products on products.id = wishlists.product_id group by product_id order by noitems desc;

    16. Selects the count and name of all products that are not on sale on the wishlist, ordered by count in descending order.


    17. Inserts a user with the name "Jonathan Anderson" into the users table. Ensure the created_at column is set to the current time.

    insert into users (created_at, name) values (CURRENT_TIMESTAMP, 'Jonathan Anderson');

    18. Selects the id of the user with the name "Jonathan Anderson"?

    select id from users where name = "Jonathan Anderson";

    19. Inserts a wishlist entry for the user with the name "Jonathan Anderson" for the product "The Ruby Programming Language".

    insert into wishlists (user_id, product_id) values (15, 4);

    20. Updates the name of the "Jonathan Anderson" user to be "Jon Anderson".

    UPDATE users SET name = "Jon Anderson" WHERE name = "Jonathan Anderson";

    21. Deletes the user with the name "Jon Anderson".

    DELETE FROM users WHERE name = "Jon Anderson";

    22. Deletes the wishlist item for the user you just deleted.

    DELETE FROM wishlists WHERE user_id = 15;
