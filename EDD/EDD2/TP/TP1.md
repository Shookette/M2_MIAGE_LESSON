# Intallation serveur Mondrian / Langage MDX

## Requêtes MDX
1. ```
select {[Measures].Members} ON COLUMNS,
{[Product].[All Products]} ON ROWS
from [SteelWheelsSales]
```
2. ```
select {(Measures.Quantity),(Measures.Sales)} ON COLUMNS,
Except
([Product].[Line].Members, [Product].[Line].[Trains]) ON ROWS
from [SteelWheelsSales]
```
3. ```
select crossjoin ({[Measures].[Quantity], [Measures].[Sales]}, {[Time].[All Years]}) ON COLUMNS,
Except
([Product].[Line].Members, [Product].[Line].[Trains]) ON ROWS
from [SteelWheelsSales]
where [Order Status].[Type].[Shipped]
```
4. ```
select {[Measures].[Quantity], [Measures].[Sales]} ON COLUMNS,
Order(Except ([Product].[Line].Members, [Product].[Line].[Trains]), [Measures].[Quantity], Desc) ON ROWS
from [SteelWheelsSales]
where [Order Status].[Type].[Shipped]
```
5. ```
select crossjoin ({[Measures].[Sales]}, {[Time].[Months].Members}) ON COLUMNS,
[Product].[All Products] ON ROWS
from [SteelWheelsSales]
where [Markets].[Country].[France]
```
6. A Modifier
```
select crossjoin ({[Measures].[Sales]}, {[Time].[Months].Members}) ON COLUMNS,
[Markets].[Canada].[City] ON ROWS
from [SteelWheelsSales]
```
