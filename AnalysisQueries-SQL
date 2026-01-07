--Meshwa Inamdar - J00739767
-- 1. Total Revenue
SELECT 
    SUM(o.Quantity * p.Price) AS TotalRevenue
FROM Orders o
JOIN Products p
    ON o.ProductID = p.ProductID;

-- 2. Revenue by Product Category
SELECT 
    p.Category,
    SUM(o.Quantity * p.Price) AS Revenue
FROM Orders o
JOIN Products p
    ON o.ProductID = p.ProductID
GROUP BY p.Category
ORDER BY Revenue DESC;

-- 3. Top Selling Products
SELECT 
    p.ProductName,
    SUM(o.Quantity) AS TotalQuantitySold
FROM Orders o
JOIN Products p
    ON o.ProductID = p.ProductID
GROUP BY p.ProductName
ORDER BY TotalQuantitySold DESC;

-- 4. Monthly Sales Trend
SELECT 
    FORMAT(o.OrderDate, 'yyyy-MM') AS Month,
    SUM(o.Quantity * p.Price) AS MonthlyRevenue
FROM Orders o
JOIN Products p
    ON o.ProductID = p.ProductID
GROUP BY FORMAT(o.OrderDate, 'yyyy-MM')
ORDER BY Month;

-- 5. Top Customers by Spend
SELECT 
    c.CustomerName,
    SUM(o.Quantity * p.Price) AS TotalSpent
FROM Orders o
JOIN Customers c
    ON o.CustomerID = c.CustomerID
JOIN Products p
    ON o.ProductID = p.ProductID
GROUP BY c.CustomerName
ORDER BY TotalSpent DESC;
