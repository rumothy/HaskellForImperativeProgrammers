# Recursion

    name <args> = ... name <args'> ...

    fac n = 
        if n <= 1 then 
            1 
        else
            n * fac (n-1)

    fac 3
    - 3 * fac 2
    -- 3 * 2 * fac 1
    --- 3 * 2 * 1
    -- 6 * 1
    - 6
    => 6

## Guards

    fac n 
    |   n <= 1  = 1
    |   otherwise = n * fac (n-1)

## Pattern Matching

    is_zero 0 = True
    is_zero _ = False

## Accumulators

    fac n = aux n 1
        where 
            aux n acc 
            | n <= 1    = acc
            | otherwises = aux (n-1) (n * acc)
