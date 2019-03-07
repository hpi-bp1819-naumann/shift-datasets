_synthetic_
# Datasets with concept shift in textual column

We used `https://github.com/hpi-bp1819-naumann/data-generator` to generate the synthetic data in this repository.


## data_text_with_bullet_points
#### Original Data Format
FileName: `data_text_with_bullet_points_p1.csv`

FileName: `data_text_with_bullet_points_multiple_columns_p1.csv` (two extra random columns)
```python
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "TEXT", "function": generator_functions.random_string},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### New Data Format
FileName: `data_text_with_bullet_points_p2.csv`

FileName: `data_text_with_bullet_points_multiple_columns_p2.csv` (two extra random columns)
```python
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "TEXT", "function": lambda a: ("'- " + str(generator_functions.random_string(a))[1:])},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
    }
```
#### Tests
| method	| passed | description |
| ------------- | -------- | ----------- |
| ML via DataWig | yes | outputs a shift of `1.0` in both the normal and extended version (without a tip which column might contain the shift) |
| name the tested method | yes/no | describe how good the shift can be detected and problems that may occur |




## data_text_with_bullet_points_5%
#### Original Data Format
FileName: `data_text_with_bullet_points_5%_p1.csv`

FileName: `data_text_with_bullet_points_5%_multiple_columns_p1.csv` (two extra random columns)
```python
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "TEXT", "function": generator_functions.random_string},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### New Data Format
FileName: `data_text_with_bullet_points_5%_p2.csv`

FileName: `data_text_with_bullet_points_5%_multiple_columns_p2.csv` (two extra random columns)
```python
def replace_func(a):
    if a % 20 == 0:
        return "'- " + str(generator_functions.random_string(a))[1:]
    else:
        return generator_functions.random_string(a)

function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "TEXT", "function": replace_func},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
    }
```
#### Tests
| method	| passed | description |
| ------------- | -------- | ----------- |
| ML via DataWig | partially yes | outputs a shift of `0.025` in the normal and a shift of `0.095` in the extended version (without a tip which column might contain the shift) |
| name the tested method | yes/no | describe how good the shift can be detected and problems that may occur |




## data_text_add_bullet_point_mod2
#### Original Data Format
FileName: `data_text_add_bullet_point_mod2_p1.csv`

FileName: `data_text_add_bullet_point_mod2_multiple_columns_p1.csv` (two extra random columns)
```python
def func_p1(a):
    w = generator_functions.random_words(a, 100)

    if a % 2 == 0:
        return "'- " + w[1:]
    else:
        return w[1:]


function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "TEXT", "function": func_p1},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### New Data Format
FileName: `data_text_add_bullet_point_mod2_p2.csv`

FileName: `data_text_add_bullet_point_mod2_multiple_columns_p2.csv` (two extra random columns)
```python
def func_p2(a):
    w = generator_functions.random_words(a, 100)

    if a % 2 == 1:
        return "'- " + w[1:]
    else:
        return w[1:]

function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "TEXT", "function": func_p2},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
    }
```
#### Tests
| method	| passed | description |
| ------------- | -------- | ----------- |
| ML via DataWig | no | cannot detect this shift |
| name the tested method | yes/no | describe how good the shift can be detected and problems that may occur |
