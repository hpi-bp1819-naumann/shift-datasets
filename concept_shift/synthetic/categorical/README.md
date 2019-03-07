_synthetic_
# Datasets with concept shift in categorical column

We used `https://github.com/hpi-bp1819-naumann/data-generator` to generate the synthetic data in this repository.

## data_categorical_histogram_fail
#### Original Data Format
FileName: `data_categorical_histogram_fail_p1.csv`

FileName: `data_categorical_histogram_fail_p1_multiple_columns_p1.csv` (two extra random columns)
```python
categories = ["A", "B", "C", "D"]
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: categories[a%4]},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### New Data Format
FileName: `data_text_with_bullet_points_p2.csv`

FileName: `data_text_with_bullet_points_multiple_columns_p2.csv` (two extra random columns)
```python
categories = ["A", "B", "C", "D"]
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: categories[(a+1)%4]},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### Tests
| method	| passed | description |
| ------------- | -------- | ----------- |
| name the tested method | yes/no | describe how good the shift can be detected and problems that may occur |
