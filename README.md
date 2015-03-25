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
