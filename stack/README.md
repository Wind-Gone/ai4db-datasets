# Stack

### Introduction

The **Stack dataset** is derived from **Stack Overflow** question-and-answer data, containing user-submitted questions, answers, and relevant metadata. It is widely used for database query optimization, text analysis, knowledge extraction, and other research scenarios. This dataset has been utilized in projects such as [**BaoForPostgreSQL**](https://github.com/learnedsystems/BaoForPostgreSQL), making it a valuable resource for academic and industrial research.

### How to Get

#### Step1

Find more details and download instructions here: 

- [**rmarcus.info/stack.html**](https://rmarcus.info/stack.html)

#### Step2

Alternatively, download the database dump file directly from:

- [**Dropbox Backup Link**](https://www.dropbox.com/scl/fi/1g0c12ddzluxm4cd7d6hm/so_pg13?rlkey=y2lvoy9c9h1xcy8t0zi61yo0r&e=1&dl=0)

Once downloaded, we can get a dataset called so_pg13 without name suffix.

You can restore the dataset into your PostgreSQL database using the following command:

```bash
pg_restore -h [ip] \
           -U [user] \
           -p [port] \
           -d [databaseName] \
           --no-owner \
           so_pg13
```

**Note**: Adjust the parameters (-h, -p, -U) according to your database environment. 

> [!TIP]
>
> Unfortunately, I am not yet aware of the exact data source, aside from the ability to install it directly into PostgreSQL.

### **Used by Papers**

The **Stack dataset** has been used in various academic and industry research papers. Below are some examples:

1. [Bao: Making Learned Query Optimization Practical](https://dl.acm.org/doi/pdf/10.1145/3448016.3452838) [SIMOD 21]
2. [Kepler: Robust Learning for Parametric Query Optimization](https://dl.acm.org/doi/pdf/10.1145/3588963) [SIGMOD 23]
3. [RankPQO: Learning-to-Rank for Parametric Query Optimization](https://github.com/songsong945/RankPQO/blob/main/RankPQO_Technical_Report.pdf) [VLDB 25]

If you have used the **Stack dataset** in your research, feel free to share your work to contribute to the community.