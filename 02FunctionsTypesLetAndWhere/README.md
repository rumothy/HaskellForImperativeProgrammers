# Functions, Types, let & where

## Function (Definitions)

    name arg1 arg2 ... argn = <expr>

## Function (Application)

    name arg1 arg2 ... argn

## Function (Examples)

    in_range min max x =
        x >= min && x <= max

    in_range 0 5 3
        => True

    in_range 4 5 3
        => False

## Types (Basics)

    name :: <type>

    x :: Integer
    x = 1

    y :: Bool
    y = True

    z :: Float
    z = 3.1415

## Types (Functions)

    in_range :: Integer -> Integer -> Integer -> Bool
    in_range min max x = x > = min && x <= max

    in_range 0.5 1.5 1 -- Type error
    in_range 0 5 3 -- Correct

## Functions (let)

    in_range min max x =
        in_lower_bound = min <= x
        in_upper_bound = max >= x
        return (in_lower_bound && in_upper_bound)

        -- This is imperative not declarative!

    in_range min max x =
        let in_lower_bound = min <= x
            in_upper_bound = max >= x
        in
        in_lower_bound && in_upper_bound

## Functions (where)

    in_range min max x = ilb && iub
        where
            ilb = min <= x
            iub = max >= x

## Functions (if)

    in_range min max x =
        if ilb then iub else False
        where
            ilb = min <= x
            iub = max >= x

## Functions (Infix)

    gchi> :t (+)
    (+) :: Num a => a -> a -> a

    add a b = a + b
    add 10 20
    10 `add` 20  -- Equivalent to the line above
