# Call Center Data v2 - Daily HOO (Hours of Operation)

## Dataset Information

**Filename**: `call-center-data-v2-daily-hoo.csv`

**Type**: Hours of Operation (HOO) variant

**Description**: This dataset contains daily call center operational metrics filtered for specific operational periods. The dataset includes null/missing values for certain dates, which may represent non-operational days or specific business hour considerations.

## Dataset Characteristics

- **Total Records**: 1,247 rows (including rows with missing values)
- **Date Range**: January 1, 2022 to May 31, 2025 (approximately)
- **Data Completeness**: Contains systematic null/missing values for certain date periods
- **Format**: CSV (Comma-Separated Values)
- **Encoding**: UTF-8

## Column Definitions

| Column Name | Data Type | Description | Unit/Format |
|-------------|-----------|-------------|-------------|
| `Date` | Date | The date of the observation | YYYY-MM-DD |
| `Incoming Calls` | Integer/Null | Total number of calls received on this date | Count |
| `Answered Calls` | Integer/Null | Number of calls answered by agents | Count |
| `Abandoned Calls` | Integer/Null | Number of calls abandoned before being answered | Count |
| `Answer Speed (AVG)` | Time Duration/Null | Average time to answer incoming calls | HH:MM:SS |
| `Talk Duration (AVG)` | Time Duration/Null | Average duration of answered calls (handle time) | HH:MM:SS |
| `Waiting Time (AVG)` | Time Duration/Null | Average time callers waited in queue | HH:MM:SS |

## Sample Data

The dataset includes periods with and without data:

```
Date,Incoming Calls,Answered Calls,Abandoned Calls,Answer Speed (AVG),Talk Duration (AVG),Waiting Time (AVG)
2022-01-01,,,,,,
2022-01-02,,,,,,
2022-01-03,317.0,304.0,13.0,0:00:18,0:01:35,0:02:37
2022-01-04,253.0,244.0,9.0,0:00:13,0:01:50,0:02:02
```

**Note**: Dates with all null values (like 2022-01-01, 2022-01-02 above) may represent weekends, holidays, or non-operational periods.

## Key Difference from Daily Dataset

### Missing Value Pattern
- This variant contains **systematic null values** for certain dates
- Missing values appear to follow a pattern (potentially weekends/holidays)
- Represents a filtered view of call center operations

### Potential Interpretations
The null values could represent:
- Non-business days (weekends, holidays)
- Hours outside of operational coverage
- Filtered data for specific business scenarios
- Days when the call center was not operational

## Usage Considerations

### Strengths
- May better represent actual operational days for capacity planning
- Null pattern itself can be informative for understanding business operations
- Potentially more relevant for workforce scheduling scenarios

### Challenges
- Requires handling of missing values in time series analysis
- May need interpolation or special treatment for forecasting models
- Gap-filling strategies will impact model performance

### Considerations for Analysis
- Understand *why* values are missing before choosing handling strategy
- Missing data pattern may be meaningful (not random)
- Consider whether forecasting should include or exclude non-operational periods

## Relevant for Milestone 1

This dataset presents opportunities to:
- **Demand Forecasting**: Predict `Incoming Calls` for operational days
- **Handle Time Prediction**: Forecast `Talk Duration (AVG)` when calls occur
- **Missing Data Handling**: Develop strategies for incomplete time series
- **Business Context Analysis**: Understand operational patterns through missing data

## Data Preparation Tips

When working with this dataset, you may need to:
- Identify and analyze the missing value pattern
- Decide on a strategy: filter missing days, impute values, or model around gaps
- Convert time duration fields (HH:MM:SS) to numeric format
- Consider whether forecasts should predict for all days or only operational days
- Explore the relationship between operational days and call patterns

## Missing Data Strategies to Consider

Different approaches for handling missing values:
1. **Exclude**: Filter out days with missing values (train only on operational days)
2. **Impute**: Fill missing values using interpolation or business rules
3. **Model**: Incorporate missingness as a feature or pattern
4. **Segment**: Model operational and non-operational days separately

The choice of strategy should be justified based on your understanding of the business problem and data characteristics.

## Related Files

- **Parent Directory**: [demand-forecasting README](README.md)
- **Alternative Dataset**: [call-center-data-v2-daily.md](call-center-data-v2-daily.md)
- **Milestone Documentation**: [Milestone 1](../../milestones/milestone-1-demand-forecasting.md)

---

**Note**: The presence of missing values in this dataset is intentional and represents an important aspect of real-world data scenarios. Your approach to handling these values should be documented and justified in your analysis.
