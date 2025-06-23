# Mechanisms Prompts

## Categorization

The same methodology as for occupations was used to categorize the mechanisms. Using the same approach as the function `run_llm` that uses a taxonomy group and the text to be categorized. 

## Prompts

### Level 2

```
"role": "system", "content": "You are going to classify texts of
work-related accidents."
```

```
"role": "user", "content": "In which of the following categories
{list_subgroups_level_2}; would you classify the text:
{input_text}. Just return one of the labels I gave you, without
final point and no additional comments."
```

### Level 3

```
"role": "system", "content": "You are going to classify
texts of work-related accidents which belongs to category
{subgroup_level_2}."
```

```
"role": "user", "content": "In which of the following categories
{list_categories_level_3} would you classify the text:
{input_text}. Just return one of the labels I gave you without a
final point and no additional comments."
```