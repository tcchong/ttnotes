# PostgreSQL

## Window Function

* OVER\(\)

## 

## Window Frames

* unbounded
* preceding
* following
* current row



Sample raw data

```

```



* default behavior is `unbounded preceding`

```
select name, sum(price) over(order by name)
from orders
```

same as

```
select name, sum(price) over(order by name range between unbounded preceding and current row)
from orders
```



### Include current row and previous N rows

* range can only be used with unbounded

```
select name, sum(price) over(order by name rows between 2 preceding and current row)
from orders
```



```
select name, sum(price) over(order by name range between current row and unbounded following)
from orders
```



```
select name, sum(price) over(order by name rows between current row and 2 following)
from orders
```



```
select name, sum(price) over(order by name rows between 2 preceding and 2 following)
from orders
```





```
select name, sum(price) over(order by name range between unbounded preceding and unbounded following)
from orders
```

same as

```
select name, sum(price) over()
from orders
order by name
```



