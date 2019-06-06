<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [gobenchmark](#gobenchmark)
- [What it is NOT](#what-it-is-not)
- [Use it](#use-it)
- [Install](#install)
- [Pre-built benchmarks](#pre-built-benchmarks)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# gobenchmark
A collection of benchmarks of basic operation, as a guide for tuning.

[![Travis-CI](https://api.travis-ci.org/openacid/low.svg?branch=master)](https://travis-ci.org/openacid/low)
[![AppVeyor](https://ci.appveyor.com/api/projects/status/1jnttodaenbrv3va/branch/master?svg=true)](https://ci.appveyor.com/project/drmingdrmer/low/branch/master)


When digging deeper and deeper into performance tuning, we found the performance
of some basic operations varies widely, in a counter-intuitive way.
These differences are critical and does impact performance.
Thus we have benchmarked basic operations, to establish a solid guide for people
working on performance critical programs.


# What it is NOT

- Cache missing or memory layout caused performance issues are not included yet.


# Use it

The statistics listed below gives us a intuitive view of basic operation performances.
**But it is strongly recommended to re-benchmark it on your platform before using it**,
since performance may vary on different architectures.


# Install

```sh
go get github.com/openacid/gobenchmark

make ben # run the benchmark
```


# Pre-built benchmarks

```txt
goos: darwin
goarch: amd64
pkg: github.com/openacid/gobenchmark
BenchmarkInt64_Multi_ByConst_Assign-8        	1000000000	         0.40 ns/op
BenchmarkInt64_Multi_ByVar_Assign-8          	1000000000	         0.42 ns/op
BenchmarkInt64_ShiftLeft_ByConst_Assign-8    	1000000000	         0.37 ns/op
BenchmarkInt64_ShiftLeft_ByVar_Assign-8      	1000000000	         0.94 ns/op
BenchmarkInt64_ShiftRight_ByConst_Assign-8   	1000000000	         0.36 ns/op
BenchmarkInt64_ShiftRight_ByVar_Assign-8     	1000000000	         1.44 ns/op
BenchmarkInt64_Div_ByConst_Assign-8          	1000000000	         0.92 ns/op
BenchmarkInt64_Div_ByVar_Assign-8            	100000000	         8.60 ns/op
BenchmarkInt64_Mod_ByConst_Assign-8          	1000000000	         1.04 ns/op
BenchmarkInt64_Mod_ByVar_Assign-8            	100000000	         8.13 ns/op
BenchmarkInt64_Assign-8                      	1000000000	         0.26 ns/op
BenchmarkFloat64_Multi_Assign-8              	1000000000	         0.78 ns/op
BenchmarkFloat64_ToInt64_Assign-8            	1000000000	         0.52 ns/op
BenchmarkFloat64_Assign-8                    	1000000000	         0.78 ns/op
PASS
ok  	github.com/openacid/gobenchmark	10.792s
```