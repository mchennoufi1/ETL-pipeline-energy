## 🎯 Project Overview

Developed an automated ETL (Extract, Transform, Load) pipeline that **reduced quarterly data processing time from days to minutes** for an energy company's analytics team. The pipeline processes electricity sales and capability data, transforming raw datasets into analysis-ready formats.

### Business Impact
- ⏱️ **Time Savings**: Automated manual process that previously took days per quarter
- 📊 **Data Quality**: Eliminated 67% of irrelevant records through intelligent filtering
- 📈 **Frequency**: Enabled monthly insights instead of quarterly updates
- 🎯 **Accuracy**: Removed 806 rows with missing data to ensure clean analysis

## 🛠️ Technical Stack

- **Language**: Python 3.8+
- **Data Processing**: Pandas
- **File Formats**: CSV, JSON, Parquet
- **Design Pattern**: ETL Pipeline Architecture

## 📋 Features

### Data Extraction
- ✅ Multi-format support (CSV, JSON, Parquet)
- ✅ Nested JSON flattening with `pd.json_normalize()`
- ✅ Robust error handling for invalid file types

### Data Transformation
- ✅ Data cleaning (remove null values)
- ✅ Sector-based filtering (residential & transportation focus)
- ✅ Date component extraction from period strings
- ✅ Column selection and restructuring
- ✅ **67% data reduction** while maintaining analytical value

### Data Loading
- ✅ Flexible output formats (CSV/Parquet)
- ✅ Optimized for downstream analytics tools
- ✅ Proper indexing for clean datasets

## 📊 Data Pipeline Flow

```
Raw Data (4,836 records)
        ↓
   [EXTRACT]
        ↓
 Read CSV/JSON files
        ↓
  [TRANSFORM]
        ↓
Remove missing prices (-806 records)
Filter sectors (-2,418 records)
Extract date components
Restructure columns
        ↓
    [LOAD]
        ↓
Clean Data (1,612 records)
```

## 📈 Performance Metrics

| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| Processing Time | Days | Minutes | ~99% faster |
| Update Frequency | Quarterly | Monthly | 3x more frequent |
| Data Quality | Manual validation | Automated validation | 100% consistent |
| Records Processed | 4,836 | 1,612 | 67% reduction |
| Missing Data | 806 nulls | 0 nulls | 100% clean |

## 🔍 Data Schema

### Input: `electricity_sales.csv`
| Field | Type | Description |
|-------|------|-------------|
| period | string | Date in YYYY-MM format |
| stateid | string | Two-letter state code |
| stateDescription | string | Full state name |
| sectorid | string | Sector identifier code |
| sectorName | string | Sector category |
| price | float | Electricity price |
| price-units | string | Price measurement unit |

### Output: Cleaned Sales Data
| Field | Type | Description |
|-------|------|-------------|
| year | string | Month extracted from period (MM) |
| month | string | Year extracted from period (YYYY) |
| stateid | string | State identifier |
| price | float | Electricity price (no nulls) |
| price-units | string | Measurement unit |

## 🎓 Skills Demonstrated

### Data Engineering
- ETL pipeline architecture
- Data validation and cleaning
- Format conversion (CSV ↔ JSON ↔ Parquet)
- Data normalization techniques

### Python Programming
- Pandas DataFrame operations
- File I/O handling
- Error handling and validation
- Modular function design
- Type hinting
