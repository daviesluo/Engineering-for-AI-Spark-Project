# NYC Taxi Data Analysis with Apache Spark

A comprehensive data analysis project using Apache Spark to process and analyse NYC taxi trip data. Implements data cleaning, feature engineering, and zone-based analysis with performance optimisation for large-scale datasets.

## Key Features
### Data Preprocessing
- Zero-value filtering
- Outlier removal using modified z-score
- Data validation and cleaning
- Missing value handling

### Feature Engineering & Analysis
- Zone name integration
- Unit profitability calculation
- Inter-zonal travel summarization
- Top-10 zone rankings by various metrics

### Performance Optimization
- Parquet and Delta format comparison
- Large-scale data processing
- Execution time analysis
- Memory optimization

## Technical Stack
### Core Technologies
- Apache Spark
- PySpark SQL
- Delta Lake

### Key Functions & Libraries
- pyspark.sql
- pyspark.sql.functions
- pandas (for auxiliary operations)
- broadcast joins
- UDFs (User Defined Functions)

### Implementation Techniques
- Vectorized operations
- Broadcast joins
- Efficient data partitioning
- Memory management

## Performance Results
### Parquet Format Performance
| Dataset Size | Rows (M) | Time w/o Task 1.2 (s) | Full Time (s) | Speed w/o 1.2 (s/1M) | Full Speed (s/1M) |
|--------------|----------|----------------------|---------------|---------------------|-----------------|
| S            | 2.90     | 6.02                | 12.34         | 2.08               | 4.26           |
| M            | 15.57    | 23.79               | 49.64         | 1.53               | 3.19           |
| L            | 41.95    | 58.14               | 136.25        | 1.39               | 3.25           |
| XL           | 90.44    | 72.64               | 159.38        | 0.80               | 1.76           |
| XXL          | 132.40   | 78.67               | 167.07        | 0.59               | 1.26           |

### Delta Format Performance
| Dataset Size | Rows (M) | Time w/o Task 1.2 (s) | Full Time (s) | Speed w/o 1.2 (s/1M) | Full Speed (s/1M) |
|--------------|----------|----------------------|---------------|---------------------|-----------------|
| S            | 2.90     | 5.34                | 11.82         | 1.84               | 4.08           |
| M            | 15.57    | 8.17                | 18.35         | 0.52               | 1.18           |
| L            | 41.95    | 8.26                | 22.19         | 0.20               | 0.53           |
| XL           | 90.44    | 14.18               | 38.90         | 0.16               | 0.43           |
| XXL          | 132.40   | 18.48               | 42.89         | 0.14               | 0.32           |

## Key Performance Insights
### Format Comparison
- Delta format consistently outperforms Parquet
- Delta shows better scaling with larger datasets
- Performance gap increases with dataset size

### Task Impact
- Task 1.2 (outlier removal) significantly impacts processing time
- Impact is more pronounced in Parquet format
- Relative overhead decreases with dataset size

### Scalability
- Both formats show improved efficiency with larger datasets
- Delta format shows superior scaling characteristics
- Processing speed per million records improves with scale
