# Big Data Processing for Distribution Analytics Using Apache Pig

---

## Project Overview

Developed big data processing scripts using Apache Pig on the Hadoop framework to analyse  medal distribution and performance trends across countries and years. The scripts handle large datasets by performing Modules such as filtering, grouping, and aggregation to compute medal counts, identify top-performing nations, and evaluate historical patterns. This project showcases the use of declarative dataflow programming in Pig for scalable and efficient big data analytics in a distributed environment.

---

## Access to Code 🔒

The source code for this project is **private** and available upon request. 

If you're an **employer** or **recruiter** and would like to review the code, please **request access via email** at **ayanhashmi205@yahoo.com**.

---

## Installation 📦

#### Prerequisites
- AWS EMR cluster with Apache Pig
- Hadoop Distributed File System (HDFS)
- Python 3.x for UDF development

#### Setup Data Files

```bash
# Upload  data files to HDFS
hdfs dfs -mkdir /input
hdfs dfs -put noc_region.csv /input/
hdfs dfs -put person_region.csv /input/
hdfs dfs -put person.csv /input/
hdfs dfs -put competitor_event.csv /input/
hdfs dfs -put medal.csv /input/
```

#### Clone and Run

```bash
# Clone the repository
git clone https://github.com/ayan9870/pig-s-analytics.git
cd pig-s-analytics

# Run individual Modules
pig -f Module1.pig
pig -f Module2-1.pig
pig -f Module2-2.pig
```

---

## Features 📋

* **Module 1**: Regional gold medal analysis
  - Aggregates gold medal counts by region
  - Implements join operations across multiple datasets
  - Sorted output by medal count (descending)

* **Module 2-1**: Multi-medal regional analysis
  - Comprehensive gold and silver medal counting
  - Complex sorting: Gold (desc) → Region (asc)
  - Handles missing medal data gracefully

* **Module 2-2**: Advanced UDF implementation
  - Custom Python User Defined Function (UDF)
  - Fills missing values with zeros
  - Enhanced sorting: Gold (desc) → Silver (desc) → Region (asc)

* **Scalability**: Designed for large-scale  datasets
* **Documentation**: Comprehensive Pig Latin comments and execution guides

---

## Architecture 🏗️

### Apache Pig Processing Pipeline

#### Module 1: Gold Medal Analysis
```
Data Loading → Join Operations → Filtering → Grouping → Aggregation → Sorting
```
- **Input**: 5 CSV files (noc_region, person_region, person, competitor_event, medal)
- **Output**: Region-wise gold medal counts
- **Key Operations**: Multi-table joins, filtering, grouping

#### Module 2-1: Multi-Medal Analysis
```
Data Loading → Complex Joins → Medal Filtering → Grouping → Aggregation → Multi-Level Sorting
```
- **Input**: Same 5 CSV files
- **Output**: Gold and silver medal counts by region
- **Key Operations**: Conditional aggregation, complex sorting

#### Module 2-2: UDF-Enhanced Analysis
```
Data Processing → UDF Application → Zero-Filling → Advanced Sorting
```
- **Input**: Module 2-1 output + Python UDF
- **Output**: Complete medal matrix with filled zeros
- **Key Innovation**: Custom Python UDF for data completeness

---

## Technical Specifications ⚙️

### Requirements
- **Platform**: Apache Pig on Hadoop cluster
- **Language**: Pig Latin with Python UDF support
- **Memory**: Optimized for large-scale data processing
- **Output**: Formatted text files with proper sorting

### HDFS Directory Structure
```
/input/
├── noc_region.csv
├── person_region.csv
├── person.csv
├── competitor_event.csv
└── medal.csv

/output/
├── Module1/
├── Module2-1/
└── Module2-2/
```

### Performance Considerations
- Efficient join strategies for multi-table operations
- Optimized grouping and aggregation operations
- Memory-efficient sorting algorithms
- Custom UDF integration for data completeness

---

## Algorithm Details 🔍

### Multi-Table Join Strategy
1. **Primary Join**: Link competitors to their regions via person_region
2. **Secondary Join**: Connect regions to readable names via noc_region
3. **Medal Join**: Associate events with medal types
4. **Aggregation**: Count medals by region and type

### Sorting Logic
- **Module 1**: Gold medals (descending)
- **Module 2-1**: Gold (desc) → Region (asc)
- **Module 2-2**: Gold (desc) → Silver (desc) → Region (asc)

---

## Results Summary 📈

| Module | Processing Type | Output Complexity | Key Innovation |
|------|----------------|------------------|----------------|
| Module 1 | Basic Join & Aggregation | Single medal type | Multi-table joins |
| Module 2-1 | Complex Aggregation | Multiple medal types | Advanced sorting |
| Module 2-2 | UDF-Enhanced | Complete data matrix | Python UDF integration |

**Performance Metrics:**
- Handles  datasets with 100k+ records
- Efficient join operations across 5 tables
- Custom UDF processing for data completeness
- Scalable sorting algorithms for large result sets

---

## Author ✨

| <a href="https://github.com/ayan9870" target="_blank">**Muhammad Ayan Hashmi**</a> |
|:--:|
| ![Ayan Hashmi](https://github.com/ayan9870.png?size=100) |
| [`github.com/ayan9870`](https://github.com/ayan9870) |

---

## License
[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
