## LDBC SNB queries and driver for TigerGraph

### Prerequisites

You first need to install all queries:

```
./install_queries.sh
```

This will install not only LDBC SNB queries but also a helper query for seed generation.

### Run driver

Once you done with installing queries, you can now run driver:

```
python3 driver.py --path [PATH_TO_SEEDS] --num [MAX_NUM_SEEDS] --query [QUERY_TYPE] --seed [NUM_SEEDS]
```

* PATH_TO_SEEDS: Full path to the directory of pre-generated seeds. Those seeds of txt files under substitution_parameters/ in generated data directory. It is by default "/home/ubuntu/ldbc_snb_data_sf1/substitution_parameters/" and you can skip this argument by directly modifying DEFAULT_PATH_TO_SEEDS in [driver.py](https://github.com/tigergraph/ecosys/blob/ldbc/ldbc_benchmark/tigergraph/queries/driver.py).
* MAX_NUM_SEEDS: Number of seeds to run queries. It will read up to MAX_NUM_SEEDS seeds from the files. It is by default 100 and you can skip this argument by directly modifying DEFAULT_MAX_NUM_SEEDS in [driver.py](https://github.com/tigergraph/ecosys/blob/ldbc/ldbc_benchmark/tigergraph/queries/driver.py).
* QUERY_TYPE (Optional): If you want to run a single query instead of all queries, you can pass a type and number of specific query: IS[1..7], IC[1..14], BI[1..25]. e.g. IS2, Ic12, bi22.
* NUM_SEEDS (Optional): If you just want to have some seed(s) to test, put the number of seeds you want to populate. It will give you person.id and message.id.