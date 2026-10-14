# TabuFuzz

1.Introduction

TabuFuzz is an AFL-based adaptive seed scheduling and energy allocation fuzzer. More details of TabuFuzz are introduced in our technical paper “Efficient Greybox Fuzzing Framework with Tabu Search”.

2.Installtion and Usage

The installation and usage of TabuFuzz are the same as those of AFL. 

3.Quick Use

./afl-fuzz -i input_seeds -o findings -- /path/to/target @@

For stdin-based targets:

./afl-fuzz -i input_seeds -o findings -- /path/to/target

4.Configuration

TabuFuzz enables both proposed modules by default.

- `AFL_TABU_SCHEDULE=0` disables tabu-search scheduling and falls back to AFL's original queue traversal.
- `AFL_TABU_ENERGY=0` disables adaptive energy allocation while keeping tabu scheduling enabled.
- Setting both variables to `0` gives an AFL-baseline-style configuration with the compatibility changes retained.

Example:

AFL_TABU_ENERGY=0 ./afl-fuzz -i in -o out -- ./target @@
