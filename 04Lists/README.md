# Lists

    [1, 2, 3, 4, 5] :: [Integer]

## Empty list

    []
    x:xs

## : prepend

    [1, 2, 3, 4, 5]
    1 : 2 : 3 : 4 : 5

## Generating a List

    asc :: Int -> Int -> [Int]
    asc m n 
    | m < n = []
    | m == n = [m]
    | m > n = n : asc (n + 1) m

    asc 1 3 
        => [1, 2, 3]

## Function on Lists

    import Data.List

    head :: [a] -> a
    head [1, 2, 3, 4, 5]
        => 5

    init :: [a] -> [a]
    init [1, 2, 3, 4, 5]
        => [1, 2, 3, 4]

    null :: [a] -> Bool
    null []
        => True

    null [1, 2, 3, 4, 5]
        => False

## Functions on Lists of Booleans

    and :: [Bool] -> Bool
    and [True, False, True]
        => False

    or :: [Bool] -> Bool
    or [True, False, True]
        => True

## List Comprehensions

    [ 2*x | x <- [1,2,3] ] => [2,4,6]
    [ 2*x | x <- [1,2,3], x > 1 ] => [4,6]

    [<gen> | <elem> <- <list>, ..., <gaurd>, ...]
    [ (x,y) | x <- [1,2,3], y <- ['a','b'] ]
        => [(1,'a'),(1,'b'),(2,'a'),(2,'b'),(3,'a'),(3,'b')]

## List Patterns

    sum :: [Int] -> Int
    sum []
    sum (x:xs) = x + sum xs

    evens :: [Int] -> Int
    evens []
    evens (x:xs)
    | mod x 2 == 0 = x : evens xs
    | otherwise = evens xs

## Tuples

    (1,2) :: (Int,Int)
    (1,'b') :: (Int, Char)

    fst :: (a,b) -> a
    fst (x,_) = x

    snd :: (a,b) -> b
    snd (_,y) = y

    let (x,y) = (1,2) in x
        => 1

    addTuples :: [(Int, Int)] -> [Int]
    addTuples xs = [ x+y | (x,y) <- xs ]
    
    addTuples [(1,2), (2,3), (100,100)]
        => [3,5,200]
