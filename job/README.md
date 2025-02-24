# JOB

### Introduction

The **Join Order Benchmark (JOB)** dataset is designed for evaluating the performance of query optimizers in relational database systems. It is based on a real-world IMDB dataset and focuses on testing join ordering strategies, making it a widely used benchmark in database research. For more details, visit the repository: [**JOB GitHub Repository**](https://github.com/danolivo/jo-bench)

### How to Get

#### Step1

Refer to this repository for setup and additional information:

- [**GitHub - JOB Benchmark**](https://github.com/danolivo/jo-bench)

#### Step2

After pulling this repository from Git, we can proceed to the next step.

I think the author has provided a clear set of instructions in the repository.

The following example demonstrates the export procedure for all tables:

```BASH
psql -f ~/jo-bench/schema.sql
psql -vdatadir="'$HOME/jo-bench'" -f ~/jo-bench/copy.sql
```

### **Used by Papers**

The **JOB dataset** has been used in various academic and industry research papers. Below are some examples:

1. [Cardinality estimation using normalizing flow](https://link.springer.com/article/10.1007/s00778-023-00808-x) [VLDBJ 24]
2. [Robust Query Driven Cardinality Estimation under Changing Workloads](https://par.nsf.gov/servlets/purl/10495282) [VLDB 23]
3. [FactorJoin: a new cardinality estimation framework for join queries](https://dl.acm.org/doi/abs/10.1145/3588721) [SIGMOD 23]
4. [Learned cardinality estimation: A design space exploration and a comparative evaluation](https://dbgroup.cs.tsinghua.edu.cn/ligl/papers/vldb22-card-exp.pdf) [VLDB 22]
5. [Are We Ready For Learned Cardinality Estimation?](https://arxiv.org/pdf/2012.06743.pdf) [VLDB 21]
6. [Cardinality Estimation in DBMS: A Comprehensive Benchmark Evaluation](https://kai-zeng.github.io/papers/benchmark_vldb_2021.pdf) [VLDB 21]

If you have used the **JOB dataset** in your research, feel free to share your work to contribute to the community.