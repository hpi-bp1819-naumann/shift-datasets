# Data Documentation

We used `https://github.com/hpi-bp1819-naumann/data-generator` to generate the synthetic data in this repository.

## data_attribute_add_const_1
#### Original Data Format
FileName: `data_attribute_add_const_1_p1.csv`

FileName: `data_attribute_add_const_1_multiple_columns_p1.csv` (two extra random columns)
```python
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: a},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### New Data Format
FileName: `data_attribute_add_const_1_p2.csv`

FileName: `data_attribute_add_const_1_multiple_columns_p2.csv` (two extra random columns)
```python
entries = 10000
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: a + 1},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
    }
```
#### Tests
| method	| passed | description |
| ------------- | -------- | ----------- |
| ML via DataWig | no | cannot detect this shift |
| name the tested method | yes/no | describe how good the shift can be detected shift and problems that may occur |



## data_attribute_add_const_10
#### Original Data Format
FileName: `data_attribute_add_const_10_p1.csv`

FileName: `data_attribute_add_const_10_multiple_columns_p1.csv` (two extra random columns)
```python
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: a},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### New Data Format
FileName: `data_attribute_add_const_10_p2.csv`

FileName: `data_attribute_add_const_10_multiple_columns_p2.csv` (two extra random columns)
```python
entries = 10000
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: a + 10},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
    }
```
#### Tests
| method	| passed | description |
| ------------- | -------- | ----------- |
| ML via DataWig | no | cannot detect this shift |
| name the tested method | yes/no | describe how good the shift can be detected shift and problems that may occur |



## data_scaled_attribute
#### Original Data Format
FileName: `data_scaled_attribute_p1.csv`

FileName: `data_scaled_attribute_multiple_columns_p1.csv` (two extra random columns)
```python
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: a},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### New Data Format
FileName: `data_scaled_attribute_p2.csv`

FileName: `data_scaled_attribute_multiple_columns_p2.csv` (two extra random columns)
```python
entries = 10000
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: 2 * a},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
    }
```
#### Tests
| method	| passed | description |
| ------------- | -------- | ----------- |
| ML via DataWig | yes | outputs a shift of `0.9625` in the normal and a shift of `0.99` extended version (without a tip which column might contain the shift) |
| name the tested method | yes/no | describe how good the shift can be detected shift and problems that may occur |



## data_scaled_attribute_div2
#### Original Data Format
FileName: `data_scaled_attribute_div2_p1.csv`
FileName: `data_scaled_attribute_div2_multiple_columns_p1.csv` (two extra random columns)
```python
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: a},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### New Data Format
FileName: `data_scaled_attribute_div2_p2.csv`
FileName: `data_scaled_attribute_div2_multiple_columns_p2.csv` (two extra random columns)
```python
entries = 10000
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: a / 2},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
    }
```
#### Tests
| method	| passed | description |
| ------------- | -------- | ----------- |
| ML via DataWig | yes | outputs a shift of `1.0` in the normal and a shift of `0.97` extended version (without a tip which column might contain the shift) |
| name the tested method | yes/no | describe how good the shift can be detected shift and problems that may occur |



## data_null_values
#### Original Data Format
FileName: `data_null_values_p1.csv`

FileName: `data_null_values_multiple_columns_p1.csv` (two extra random columns)
```python
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: a},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### New Data Format
FileName: `data_null_values_p2.csv`

FileName: `data_null_values_multiple_columns_p2.csv` (two extra random columns)
```python

def func(a):
    if a % 20 == 0:
        return None
    else:
        return a

function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": func},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
    }
```
#### Tests
| method	| passed | description |
| ------------- | -------- | ----------- |
| ML via DataWig | partially yes | outputs a shift of `0.0425` in the normal and a shift of `0` extended version (without a tip which column might contain the shift) |
| name the tested method | yes/no | describe how good the shift can be detected shift and problems that may occur |




## data_histogram_fail
A simple Histogram check will fail this test.
#### Original Data Format
FileName: `data_histogram_fail_p1.csv`

FileName: `data_histogram_fail_multiple_columns_p1.csv` (two extra random columns)
```python
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: a},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
}
```
#### New Data Format
FileName: `data_histogram_fail_p2.csv`

FileName: `data_histogram_fail_multiple_columns_p2.csv` (two extra random columns)
```python
entries = 10000
function_list = {
    "idx": {"sql_type": "INTEGER", "function": lambda a: a},
    "att1": {"sql_type": "INTEGER", "function": lambda a: entries - a},
    "random_string": {"sql_type": "TEXT", "function": generator_functions.random_string}, # random columns just in extended dataset
    "random_int": {"sql_type": "INTEGER", "function": generator_functions.random_int} # random columns just in extended dataset
    }
```
#### Tests
| method	| passed | description |
| ------------- | -------- | ----------- |
| ML via DataWig | yes | outputs a shift of `1.0` in the normal and a shift of `0.985` in the extended version (without a tip which column might contain the shift) |
| name the tested method | yes/no | describe how good the shift can be detected shift and problems that may occur |


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
| name the tested method | yes/no | describe how good the shift can be detected shift and problems that may occur |




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
| name the tested method | yes/no | describe how good the shift can be detected shift and problems that may occur |




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
| name the tested method | yes/no | describe how good the shift can be detected shift and problems that may occur |
