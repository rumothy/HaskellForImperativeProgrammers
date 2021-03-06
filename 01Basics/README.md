# Prerequisites

- Imperitive programming (C, C++, Python, Java)
- Basic theory on programming language (Types, Evaluation, Compilers, Interpreters)
- Haskell Toolchain (ghc, ghci, cabal)
- Ghci

# Functional Programming

- Pure(mathematical) functions
- Immutable data
- No/Less side-effects
- Declarative
- Easier to verify

# Declarative vs. Imperative

### Imperative

    int sum(int *arr, int length) {
        int i, sum = 0;
        for (i = 0; i < length; i++) {
            sum += arr[i];
        }
        return sum;
    }

### Declarative

    sum [] = 0
    sum (x:xs) = x + sum xs

-or-

    sum = foldr (+) 0

# Lazy vs. Strict

### Strict

    int func(int arg) {

        int x = func1(arg);
        int y = func2(arg);
        int z = func3(arg);

        if (z)
            return x;
        else
            return y;
    }

### Lazy

    func arg =
        let x = func1 arg
            y = func2 arg
            z = func3 arg
        in
        if z then x else y
