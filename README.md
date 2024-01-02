# Reliable Text-to-SQL on Electronic Health Records @ NAACL - Clinical NLP 2024

<p align="left" float="left">
  <img src="image/logo.png" height="100" />
</p>


[Competition](#competition) | [Data Source](#data_source) | [Data Format](#data_format) | [Evaluation Metrics](#scorer_and_official_evaluation_metrics) | [Baselines](#baselines) | [FAQ](#faq) | [Organizers](#organizers) | [Contacts](#contacts)


Electronic Health Records (EHRs) are relational databases that store a patient’s entire medical history in the hospital. From hospital admission to patient treatment and discharge, EHRs record and store various medical events that occur during a patient's hospital stay. While they are invaluable sources of clinical knowledge, exploring them beyond a pre-defined set of queries typically requires proficiency in query languages such as SQL. An alternative approach is to build a text-to-SQL system that can automatically translate natural language questions directly into the corresponding SQL queries.

The goal of the task is to develop a 'reliable text-to-SQL system on EHRs.' Unlike standard text-to-SQL tasks, this system must handle all types of questions, including answerable and unanswerable ones with respect the the EHR database strcture. For answerable questions, the system must accurately generate SQL queries. For unanswerable questions, the system must correctly identify them as such, thereby preventing incorrect SQL predictions for infeasible questions. The range of questions includes answerable queries about MIMIC-IV, covering topics such as patient demographics, vital signs, and specific disease survival rates ([EHRSQL](https://github.com/glee4810/EHRSQL)). Additionally, there are specially designed unanswerable questions intended to challenge the system. Successfully completing this task will result in the creation of a reliable question-answering system for EHRs, significantly improving the flexibility and efficiency of clinical knowledge exploration in hospitals.



## Competition

Our competition is launched on the CodaBench platform: [https://www.codabench.org/competitions/XXX](https://www.codabench.org/competitions/XXX).



## <a name="data_format"></a>Data Format

### Statistics
| #Train | #Dev | #Test |
|--------:|--------:|--------:|
| 9680 (TBD) | 1260 (TBD) | 1698 (TBD) |


### Data Format

For the task, we have two types of files for each of the train, dev, and test sets: data files (with names like \*_data.json) and label files (with names like \*_label.json). Data files contain the input data for the model, and label files contain the expected model outputs that share the same 'id's as the corresponding data files.
#### Input Data (\*_data.json)
A list of python dictionary in the JSON format:
```
{
  id -> Identifier of the example,
  question -> Input question (This can be either answerable or unanswerable given the MIMIC-IV schema)
}
```

#### Output Data (\*_label.json)
A list of python dictionary in the JSON format:
```
{
  id -> Identifier of the example,
  label -> Label (SQL query or 'null')
}
```


## Baseline

### Option 1: Local-Model Sample Submission



### Option 2: OpenAI Model Sample Submission





## Submission

### File Format and Format Checkers

A prediction file must be one single JSON file for all texts. The entry for each text must include the fields "id" and "label", same as \*_label.json.
The format checkers verify that your prediction file complies with the expected format. They are located in the ```format_checker``` module.
```python
python3 format_checker/format_checker.py --pred_files_path=<path_to_your_results_files> 
```


## Organizers

Organizers are from [EdLab](https://mp2893.com/) @ [KAIST AI](https://gsai.kaist.ac.kr/).

- Edward Choi
- Gyubok Lee
- Sunjun Kweon
- Seongsu Bae

## Contacts

Google group: [https://groups.google.com/g/ehrsql/](https://https://groups.google.com/g/ehrsql-2024/)  
Email: ehrsql-2024@googlegroups.com