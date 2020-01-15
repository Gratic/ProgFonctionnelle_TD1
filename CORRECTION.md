 > **Question 1.1**
> * N opérations
```scala
def puissance(x:Int,n:Int):Int =
{
    (n,(n%2)) match
    {
        case (0,_)   => 1
        case (1,_)   => x
        case (_, 0)  =>  puissance(x*x,(n/2))
        case _   => x*puissance(x*x,(n-1)/2)
    }
}
 ```
 > **Question 1.2**
```scala
def show(f: Int => Int, xs: List[Int]):Unit =
{
   for (x <- xs) {
    println(f(x))
  }
}
show(x => x*x,List(1,2,3,4))
 ```


> **Question 2**

```scala
def syracuse(u:Int):Long =
{
    def syracuseRec(u:Int,n:Int):Long =
    {
        (u,(u%2)) match
        {
            case (1,_) => n
            case (_,0) => syracuseRec(u/2,n+1)
            case _ =>  syracuseRec(3*u+1,n+1)
        }
    }
   syracuseRec(u,0) 
}
```

> **Question 3**

```scala
def fib(n:Int):Long =
{
   n match
   {
      case 0 | 1 => n
      case n =>  fib(n-1)+fib(n-2)
   }
}
```

> **Question 5**
```scala
def fib_tr( n: Int, b: Long, a: Long): Long=
{
    n match
    {
        case 0 => a
        case _ => fib_tr( n -1, a + b, b)
    }
}
```