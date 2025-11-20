# Call Center Data v2 - Daily (Complete)

## Dataset Information

**Filename**: `call-center-data-v2-daily.csv`

**Type**: Complete daily dataset

**Description**: This dataset contains comprehensive daily call center operational metrics with complete data coverage across all dates in the observation period.

## Dataset Characteristics

- **Total Records**: 1,247 daily observations
- **Date Range**: January 1, 2022 to May 31, 2025 (approximately)
- **Data Completeness**: All dates in the time period are populated with values
- **Format**: CSV (Comma-Separated Values)
- **Encoding**: UTF-8

## Column Definitions

| Column Name | Data Type | Description | Unit/Format |
|-------------|-----------|-------------|-------------|
| `Date` | Date | The date of the observation | YYYY-MM-DD |
| `Incoming Calls` | Integer | Total number of calls received on this date | Count |
| `Answered Calls` | Integer | Number of calls answered by agents | Count |
| `Abandoned Calls` | Integer | Number of calls abandoned before being answered | Count |
| `Answer Speed (AVG)` | Time Duration | Average time to answer incoming calls | HH:MM:SS |
| `Talk Duration (AVG)` | Time Duration | Average duration of answered calls (handle time) | HH:MM:SS |
| `Waiting Time (AVG)` | Time Duration | Average time callers waited in queue before being answered | HH:MM:SS |

## Sample Data

The dataset begins with dates from January 2022:

```
Date,Incoming Calls,Answered Calls,Abandoned Calls,Answer Speed (AVG),Talk Duration (AVG),Waiting Time (AVG)
2022-01-01,157,145,12,0:00:15,0:02:29,0:03:12
2022-01-02,37,37,0,0:00:03,0:02:06,0:00:35
2022-01-03,317,304,13,0:00:18,0:01:35,0:02:37
```

## Key Metrics Explained

### Call Volume Metrics
- **Incoming Calls**: The demand metric—represents total call volume
- **Answered Calls**: Successful service completions
- **Abandoned Calls**: Calls where customers hung up before reaching an agent

### Time-Based Metrics
- **Answer Speed**: Service level indicator (how quickly calls are answered)
- **Talk Duration**: Handle time—critical for capacity planning and forecasting
- **Waiting Time**: Customer experience metric—time in queue before service

## Usage Considerations

### Strengths
- Complete time series with no missing dates
- Includes all calendar days (weekdays, weekends, holidays)
- Provides comprehensive view of call center operations

### Considerations for Analysis
- May include days with varying operational patterns (business days vs. weekends/holidays)
- All dates have values, which simplifies time series modeling
- Consider whether all dates are equally relevant for forecasting operational demand

## Relevant for Milestone 1

This dataset is suitable for:
- **Demand Forecasting**: Predicting `Incoming Calls` volume
- **Handle Time Prediction**: Forecasting `Talk Duration (AVG)`
- **Time Series Analysis**: Complete dataset enables standard time series techniques
- **Pattern Recognition**: Identifying daily, weekly, and seasonal patterns

## Data Preparation Tips

When working with this dataset, you may want to consider:
- Converting time duration fields (HH:MM:SS) to numeric format (seconds or minutes)
- Creating date-based features (day of week, month, holiday indicators)
- Handling the relationship between incoming, answered, and abandoned calls
- Exploring patterns in service level metrics over time

## Related Files

- **Parent Directory**: [demand-forecasting README](README.md)
- **Alternative Dataset**: [call-center-data-v2-daily-hoo.md](call-center-data-v2-daily-hoo.md)
- **Milestone Documentation**: [Milestone 1](../../milestones/milestone-1-demand-forecasting.md)

---

**Note**: This documentation provides structural information about the dataset. Detailed exploration and analysis are part of your milestone deliverables.
