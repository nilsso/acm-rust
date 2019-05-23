Arithmetic Congruence Monoid
============================

Implements [arithmetic congruence monoids][math-acm] (ACM) in Rust.

[math-acm]: http://faculty.fairfield.edu/pbaginski/Papers/SubmittedACMSurvey%20RevisedReferee%2001.20.2013.pdf

In a nutshell, an ACM is an arithmetic progression which possesses a multiplicative structure,
and specifically is the monoid:
<center>
<img src="img//2.png" height=24pt>
</center>

With <img src="img//0.png" height=14pt> and <img src="img//1.png" height=14pt> we get a Hilbert monoid:
<center>
<img src="img//3.png" height=24pt>
</center>

Over an ACM, we can factor integers into elements of the ACM. This is similar to
simple prime factorization except that each factor must be an element of the
ACM. We call elements which cannot be expressed as the product of smaller ACM
elements *atoms*.

Finally, the purpose of this library is to study the atomic density of different
ACMs, that is, the distance between atoms. In certain ACMs the atomic density is
provably constant throughout, but in others it is unknown, not dissimilar to the
density, or lack thereof, of prime integers in the set of all integers.

## CLI
First build:
```
cargo b
```
Provided is a CLI program `acm_rust` with subcommands to test the main ACM
module and the divisors/factorize submodules.
```
> ./target/debug/acm_rust ACM 3 6 F 225 -v
ACM(3,6) prime power factorization of 225 : [[15, 15], [3, 75]]
```

For full usage lists try it and any subcommand with the `-h` flag:
```
> ./target/debug/acm_rust -h
USAGE:
    acm_rust [FLAGS] [SUBCOMMAND]

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information
    -v               Set verbose output

SUBCOMMANDS:
    ACM     ArithmeticCongruenceMonoid subcommand
    D       Integer divisors subcommand
    F       Integer factorization subcommand
    help    Prints this message or the help of the given subcommand(s)
```

<!--
   -
   -## Submodules
   -
   -### Prime power factorization
   -The [`factorize`][factorize] submodule provides a function `factorize` which
   -given an integer returns a vector of pairs of prime integer factors and powers
   -(the number of times it is a factor). For example:
   -```rust
   -assert_eq!(prime_factors::factorize(420), vec![(2, 2), (3, 1), (5, 1), (7, 1)]);
   -```
   -
   -[factorize]: https://github.com/nilsso/acm_rust/blob/master/src/factorize.rs
   -
   -### Divisors
   -The [`divisors`][divisors] submodule provides a function `divisors` which given an
   -integer returns a vector of integer divisors.
   -For example:
   -```rust
   -assert_eq!(divisors::divisors(18), vec![1, 2, 3, 9, 6, 18]);
   -```
   -
   -[divisors]: https://github.com/nilsso/acm_rust/blob/master/src/divisors.rs
   -->

## Documentation
Build all documentation and open in your browser:
```
cargo doc --all --open
```

## Tests
```
cargo t
```
