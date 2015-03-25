# Practicas
use Northwind

--1.- Listar todos los clientes

select *
from Customers

--2.- Listar todos los clientes ordenado por nombre de la empresa

select *
from Customers
order by CompanyName

--3.- Listar todos los clientes de Venezuela

select *
from Customers
where Country = 'Venezuela'

--4.- Listar todos los clientes de Venezuela cuyo nombre empieze por C

select *
from Customers
where (Country = 'Venezuela') and (ContactName LIKE 'C%')

--5.- Listar todos los pedidos con ShipRegion en NULL

select *
from Orders
where ShipRegion is NULL

--6.- Listar los paises donde existen clientes. Sin repetir el pais

select DISTINCT country
from Customers

--7.- Listar el numero de clientes por pais

select country, count (*) AS Cantidad
from Customers
GROUP by Country


--8.- Listar los paises con mas de 5 clientes

select country, count (*) AS Cantidad
from Customers
GROUP by Country
having Count (*) > 5

--9.- Listar los dos paises donde hay mas clientes

select top (2) country, count (*) AS Cantidad
from Customers
GROUP by Country
Order by 2 desc

--10.- Listar el nombre de los productos vendidos durante el año 1997

select DISTINCT P.ProductName
from [Order Details] as OD join Orders as O on (OD.OrderID = O.OrderID) join products as P on (OD.productID = P.productid)
where datepart(yyyy,O.OrderDate) = '1997'

