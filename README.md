# Premier League Club Investment Analysis

## Project Overview
Company ABC seeks to invest in English Premier League clubs with high growth potential, excluding those already owned by competitors. This analysis evaluates historical performance data to identify optimal investment targets.

## Objectives
- Identify top-performing clubs based on key metrics
- Analyze clubs with untapped potential
- Provide data-driven investment recommendations

## Data Dictionary
| Column | Description | Key Insights |
|--------|-------------|--------------|
| `Club` | Team name | - |
| `Matches` | Total EPL matches | Manchester United (1,148) leads |
| `Wins` | All-time victories | Used to calculate win rate |
| `Clean Sheets` | Matches without conceding | Key defensive metric |
| `TeamLaunch` | Founding year | Legacy vs new clubs |
| `Winners` | League titles | Man City (6) leads since 2010 |
| `Runners-up` | Second-place finishes | Liverpool (5) recent contender |

## Methodology
### 1. Data Preparation
- Handled null values:
  - `Winners/Runners-up`: Set to 0 (domain knowledge)
  - `Lastplayed`: Formatted to 'YYYY'
- Created derived metrics:
  ```python
  df['Win_Rate'] = (df['Wins']/df['Matches'])*100
  df['CS_Rate'] = (df['Clean Sheets']/df['Matches'])*100
  ```

### 2. Key Analysis
- **Performance Scoring**:
  - Weighted combination of win rate, clean sheets, and titles
- **Outlier Handling**:
  - Retained exceptional performers (Leicester City 2016)
- **Recency Adjustment**:
  - Prioritized active clubs (`Lastplayed > 2018`)

## Key Findings
### Top Investment Targets
1. **Leicester City** 🏆
   - 2016 Premier League winners
   - Consistent top-10 finishes
   - High clean sheet rate (38%)

### Clubs to Avoid
- Inactive teams (`Lastplayed < 2010`)
- Legacy clubs with declining metrics

## Recommendations
1. **Immediate Investment**:
   - Leicester City (proven success)
   - Brighton (data-driven approach)

2. **Development Projects**:
   - Brentford FC (analytics-focused)
   - Crystal Palace (stable mid-table)

3. **Long-term Holds**:
   - Newcastle United (new ownership)
   - West Ham (European competition)




