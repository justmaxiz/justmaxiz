Заказы с ID сотрудника, равным 4:
```sql
SELECT * FROM Orders where EmployeeID = 4;
```

Список продуктов, где в единице измерений присутствует "box":
```sql
SELECT * FROM Products where Unit like "%box%";
```

Список пользователей из Мексики:
```sql
SELECT * FROM Customers where Country = "Mexico";
```

Кол-во заказов из Мексики с продуктом "Ikura":
```sql
SELECT COUNT(od.ProductID) AS OrdersCount

FROM (orders o

      INNER JOIN customers c ON o.customerid = c.customerid)

     INNER JOIN OrderDetails od ON o.OrderID = od.OrderID

WHERE c.country = 'mexico'

  AND od.ProductID = 10

GROUP BY o.OrderID;
```