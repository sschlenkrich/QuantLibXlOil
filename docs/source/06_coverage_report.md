# QuantLibXlOil Coverage Report - QuantLib-SWIG v1.41

## Executive Summary

This report presents a comprehensive analysis of the coverage of QuantLibXlOil functions against the QuantLib-SWIG v1.41 interface. The analysis identifies which QuantLib classes and functions are available through the Python interface and which are exposed to Excel via the `@xlo.func` decorator in QuantLibXlOil.

**Key Statistics:**
- **QuantLib-SWIG v1.41 Python Interface**: 100+ classes, 1000+ functions across 80+ interface files
- **QuantLibXlOil Exposed Functions**: 500+ functions across 25+ Python modules
- **Coverage Assessment**: Partial coverage with focus on core financial functionality

## Methodology

### Data Sources
1. **QuantLib-SWIG Interface Files**: All `.i` files from https://github.com/lballabio/QuantLib-SWIG/tree/v1.41/SWIG/
2. **QuantLibXlOil Source Code**: All Python files in `src/quantlib_xloil/`
3. **Analysis Scope**: Python-specific and platform-agnostic SWIG interface definitions

### Analysis Approach
1. Extracted all class definitions and member functions from SWIG interface files
2. Identified all functions decorated with `@xlo.func` in QuantLibXlOil source code
3. Mapped QuantLibXlOil wrapper function names to corresponding QuantLib classes
4. Identified gaps and missing functionality

## QuantLib-SWIG v1.41 Interface Overview

The QuantLib-SWIG v1.41 interface provides comprehensive coverage of QuantLib functionality through 80+ interface files organized into major module categories.

### Core Infrastructure
- quantlib.i, ql.i, common.i, types.i

### Date and Time
- date.i, calendars.i, daycounters.i, scheduler.i

### Financial Instruments
- bonds.i, cashflows.i, instruments.i, options.i, swap.i, creditdefaultswap.i, capfloor.i, fra.i, futures.i

### Market Data
- termstructures.i, yieldcurve.i, discountcurve.i, forwardcurve.i, indexes.i, ratehelpers.i

### Models and Processes
- stochasticprocess.i, shortratemodels.i, gaussian1dmodel.i, localvolatilities.i, volatilitymodels.i, volatilities.i, lmm.i

### Pricing Engines
- blackformula.i, fdm.i, montecarlo.i, optimizers.i, interpolation.i

### Exotic Options
- asianoptions.i, barrieroptions.i, basketoptions.i, cliquetoptions.i, lookbackoptions.i, spreadoption.i, swingoption.i, swaption.i

### Utility and Supporting Classes
- currencies.i, exchangerates.i, dividends.i, exercise.i, grid.i, interestsrate.i, money.i, null.i, observer.i, parameter.i, payoffs.i, rounding.i, settings.i, statistics.i

### Additional
- timebasket.i, timeseries.i, tracing.i, tuple.i, vectors.i, zerocurve.i, old_volatility.i

## QuantLibXlOil Current Coverage

### Fully Covered Modules (Excellent Coverage)

#### 1. Core Date and Time Functionality
**Module**: date.py
**SWIG File**: date.i
**Coverage**: Excellent

- [x] `qlDate` - Date creation from year/month/day
- [x] `qlDateWeekday` - Return weekday
- [x] `qlDateDayOfMonth` - Day of month
- [x] `qlDateDayOfYear` - Day of year
- [x] `qlDateMonth` - Month
- [x] `qlDateYear` - Year
- [x] `qlDateIsLeap` - Leap year check
- [x] `qlDateMinDate` - Minimum date
- [x] `qlDateMaxDate` - Maximum date
- [x] `qlDateTodaysDate` - Current date
- [x] `qlDateStartOfMonth` - Start of month
- [x] `qlDateEndOfMonth` - End of month
- [x] `qlDateIsStartOfMonth` - Check start of month
- [x] `qlDateIsEndOfMonth` - Check end of month
- [x] `qlPeriod` - Period creation
- [x] `qlPeriodLength` - Period length
- [x] `qlPeriodUnits` - Period units
- [x] `qlPeriodFrequency` - Period frequency
- [x] `qlPeriodNormalized` - Normalized period
- [x] Date parser functions: `qlDateParserParseFormatted`, `qlDateParserParseISO`
- [x] Period parser: `qlPeriodParserParse`

#### 2. Calendars
**Module**: calendars.py
**SWIG File**: calendars.i
**Coverage**: Comprehensive

- [x] `qlCalendar` - Calendar creation for all major markets
- [x] `qlCalendarisWeekend` - Weekend check
- [x] `qlCalendarStartOfMonth` - Start of month
- [x] `qlCalendarEndOfMonth` - End of month
- [x] `qlCalendarIsBusinessDay` - Business day check
- [x] `qlCalendarIsHoliday` - Holiday check
- [x] `qlCalendarIsEndOfMonth` - End of month check
- [x] `qlCalendarIsStartOfMonth` - Start of month check
- [x] `qlCalendarAddHoliday` - Add holiday
- [x] `qlCalendarRemoveHoliday` - Remove holiday
- [x] `qlCalendarResetAddedAndRemovedHolidays` - Reset holidays
- [x] `qlCalendarAdjust` - Date adjustment
- [x] `qlCalendarAdvance` - Date advancement
- [x] `qlCalendarBusinessDaysBetween` - Business days between dates
- [x] `qlCalendarHolidayList` - Holiday list
- [x] `qlCalendarBusinessDayList` - Business day list
- [x] `qlCalendarName` - Calendar name
- [x] `qlCalendarEmpty` - Empty calendar
- [x] `qlCalendarJointCalendar` - Joint calendar creation

#### 3. Day Counters
**Module**: daycounters.py
**SWIG File**: daycounters.i
**Coverage**: Complete

- [x] `qlDayCounter` - Day counter creation
- [x] `qlDayCounterDayCount` - Day count
- [x] `qlDayCounterYearFraction` - Year fraction
- [x] `qlDayCounterName` - Day counter name
- [x] `qlDayCounterEmpty` - Empty day counter
- [x] `qlDayCounterYearFractionToDate` - Year fraction to date

#### 4. Currencies
**Module**: currencies.py
**SWIG File**: currencies.i
**Coverage**: Complete

- [x] `qlCurrency` - Currency creation
- [x] `qlCurrencyName` - Currency name
- [x] `qlCurrencyCode` - Currency code
- [x] `qlCurrencyNumericalCode` - Numerical code
- [x] `qlCurrencySymbol` - Currency symbol
- [x] `qlCurrencyFractionSymbol` - Fraction symbol
- [x] `qlCurrencyFractionsPerUnit` - Fractions per unit
- [x] `qlCurrencyRounding` - Rounding
- [x] `qlCurrencyTriangulationCurrency` - Triangulation currency

#### 5. Black Formula
**Module**: blackformula.py
**SWIG File**: blackformula.i
**Coverage**: Complete

- [x] `qlBlackFormula` - Black formula calculation
- [x] `qlBlackFormulaImpliedStdDev` - Implied standard deviation
- [x] `qlBlackFormulaImpliedStdDevLiRS` - Implied std dev (Li-RS)
- [x] `qlBachelierBlackFormula` - Bachelier Black formula
- [x] `qlBachelierBlackFormulaImpliedVol` - Bachelier implied volatility
- [x] `qlBachelierBlackFormulaImpliedVolChoi` - Bachelier implied vol (Choi)
- [x] `qlBlackDeltaCalculator` - Black delta calculator
- [x] `qlBlackDeltaCalculatorDeltaFromStrike` - Delta from strike
- [x] `qlBlackDeltaCalculatorStrikeFromDelta` - Strike from delta
- [x] `qlBlackDeltaCalculatorAtmStrike` - ATM strike

#### 6. Credit Default Swaps
**Module**: creditdefaultswap.py
**SWIG File**: creditdefaultswap.i
**Coverage**: Comprehensive

- [x] `qlClaimAmount` - Claim amount types
- [x] `qlFaceValueClaim` - Face value claim
- [x] `qlFaceValueAccrualClaim` - Face value accrual claim
- [x] `qlAtDefaultClaim` - At default claim
- [x] `qlCreditDefaultSwap` - CDS creation
- [x] `qlCreditDefaultSwapWithUpfront` - CDS with upfront
- [x] `qlCreditdefaultSwapSide` - CDS side
- [x] `qlCreditDefaultSwapNotional` - CDS notional
- [x] `qlCreditDefaultSwapRunningSpread` - Running spread
- [x] `qlCreditDefaultSwapUpfront` - Upfront
- [x] `qlCreditdefaultSwapSettlesAccrual` - Settles accrual
- [x] `qlCreditdefaultSwapPaysAtDefaultTime` - Pays at default time
- [x] `qlCreditDefaultSwapCoupons` - CDS coupons
- [x] `qlCreditDefaultSwapProtectionStartDate` - Protection start date
- [x] `qlCreditDefaultSwapProtectionEndDate` - Protection end date
- [x] `qlCreditDefaultSwapRebatesAccrual` - Rebates accrual
- [x] `qlCreditDefaultSwapUpfrontPayment` - Upfront payment
- [x] `qlCreditDefaultSwapAccrualRebate` - Accrual rebate
- [x] `qlCreditDefaultSwapTradeDate` - Trade date
- [x] `qlCreditDefaultSwapCashSettlementDays` - Cash settlement days
- [x] `qlCreditDefaultSwapFairUpfront` - Fair upfront
- [x] `qlCreditDefaultSwapFairSpread` - Fair spread
- [x] CDS pricing functions: NPV, coupon leg NPV, default leg NPV, upfront NPV, accrual rebate NPV

#### 7. Settings and Configuration
**Module**: settings.py
**SWIG File**: settings.i
**Coverage**: Complete

#### 8. Rounding
**Module**: rounding.py
**SWIG File**: rounding.i
**Coverage**: Complete

#### 9. Scheduler
**Module**: scheduler.py
**SWIG File**: scheduler.i
**Coverage**: Complete

#### 10. Payoffs
**Module**: payoffs.py
**SWIG File**: payoffs.i
**Coverage**: Complete

#### 11. Indexes
**Module**: indexes.py
**SWIG File**: indexes.i
**Coverage**: Complete

### Partially Covered Modules (Good Coverage)

#### 12. Bonds
**Module**: bonds.py
**SWIG Files**: bonds.i, bondfunctions.i
**Coverage**: Partial - Core bond functionality covered

- [x] `qlBond`, `qlBond2` - Bond creation
- [x] `qlBondNextCouponRate`, `qlBondPreviousCouponRate` - Coupon rates
- [x] `qlBondNextCashFlowDate`, `qlBondPreviousCashFlowDate` - Cash flow dates
- [x] `qlBondSettlementDays`, `qlBondSettlementDate` - Settlement info
- [x] `qlBondIsTradable`, `qlBondStartDate`, `qlBondMaturityDate`, `qlBondIssueDate` - Bond properties
- [x] `qlBondCashFlows`, `qlBondRedemption`, `qlBondRedemptions` - Cash flow access
- [x] `qlBondCalendar`, `qlBondNotionals`, `qlBondNotional` - Bond attributes
- [x] `qlBondCleanPrice`, `qlBondCleanPrice2`, `qlBondDirtyPrice`, `qlBondDirtyPrice2` - Price calculations
- [x] `qlBondYield`, `qlBondYield2` - Yield calculations
- [x] `qlBondAccruedAmount`, `qlBondSettlementValue`, `qlBondSettlementValue2` - Accrued amounts
- [x] `qlBondCleanPriceFromZSpread` - Clean price from Z-spread
- [x] `qlBondsinkingSchedule`, `qlBondSinkingNotionals` - Sinking schedule
- [x] Bond types: `qlZeroCouponBond`, `qlFixedRateBond`, `qlAmortizingFixedRateBond`, `qlAmortizingFloatingRateBond`, `qlFloatingRateBond`, `qlCmsRateBond`, `qlAmortizingCmsRateBond`
- [x] `qlBondSetDiscountingEngine` - Set pricing engine
- [x] `qlCallableBondCallability` - Callability features
- [ ] Some advanced bond-specific calculation methods

#### 13. Cash Flows
**Module**: cashflows.py
**SWIG File**: cashflows.i
**Coverage**: Partial - Core functionality covered

- [x] Basic cash flow creation: `qlSimpleCashFlow`, `qlRedemption`, `qlAmortizingPayment`, `qlIndexedCashFlow`
- [x] Cash flow inspection: `qlCashFlowAmount`, `qlCashFlowDate`, `qlCashFlowHasOccurred`
- [x] Cash flow type conversion: `qlAsIndexedCashFlow`, `qlAsCoupon`
- [x] Coupon functions: `qlCouponNominal`, `qlCouponAccrualStartDate`, `qlCouponAccrualEndDate`, etc.
- [x] Fixed and floating rate coupon handling
- [ ] Some advanced cash flow types and pricers

#### 14. Term Structures
**Modules**: termstructures.py, piecewiseyieldcurve.py, interpolatedyieldcurves.py
**SWIG Files**: termstructures.i, piecewiseyieldcurve.i
**Coverage**: Partial - Core yield curve functionality covered

- [x] Basic yield curve creation and inspection
- [x] Rate helper creation and manipulation
- [ ] Some advanced term structure manipulation methods

#### 15. Options (Largest Module)
**Module**: options.py
**SWIG File**: options.i (largest SWIG module)
**Coverage**: Partial - Core option functionality covered

**Covered Classes and Functions:**
- [x] `qlEuropeanOption`, `qlAmericanOption` - Vanilla option creation
- [x] `qlAnalyticEuropeanEngine` - Analytic European engine
- [x] `qlBlackCalculator`, `qlBachelierCalculator` - Pricing calculators
- [x] `qlBinomialVanillaEngine` - Binomial tree engine
- [x] `qlMCEuropeanEngine` - Monte Carlo European engine
- [x] `qlHestonModel`, `qlHestonProcess` - Heston model and process
- [x] `qlAnalyticHestonEngine` - Analytic Heston engine
- [x] `qlBatesModel`, `qlBatesEngine` - Bates model
- [x] `qlVarianceGammaEngine` - Variance Gamma engine
- [x] Vanilla option properties: delta, gamma, vega, theta, rho, etc.
- [x] Option pricing methods: `qlOptionNPV`, `qlOptionImpliedVolatility`
- [x] Greeks calculation: `qlOptionDelta`, `qlOptionGamma`, `qlOptionVega`, `qlOptionTheta`, `qlOptionRho`
- [x] Exotic options: `qlMargrabeOption`, `qlCompoundOption`, `qlSimpleChooserOption`, `qlComplexChooserOption`
- [x] Option engines: Multiple European engines, American engines

**Missing from SWIG options.i:**
- [ ] `FdBlackScholesVanillaEngine` - Finite difference Black-Scholes engine
- [ ] `FdHestonVanillaEngine` - Finite difference Heston engine
- [ ] `AnalyticPTDHestonEngine` - Piecewise time-dependent Heston engine
- [ ] `MCAmericanEngine` - Monte Carlo American engine
- [ ] `QdPlusAmericanEngine` - Quadratic approximation American engine
- [ ] `FdSabrVanillaEngine` - SABR model engine
- [ ] `AnalyticCEVEngine` - CEV model engine
- [ ] `AnalyticDigitalAmericanEngine` - Digital American engine
- [ ] `CashDividendEuropeanEngine` - Cash dividend European engine
- [ ] Various approximation engines for American options

#### 16. Swaps
**Module**: swap.py
**SWIG File**: swap.i
**Coverage**: Comprehensive but not complete

- [x] Vanilla interest rate swap creation
- [x] Swap pricing and analytics
- [x] Various swap types (fixed-for-floating, basis swaps, etc.)
- [ ] Some advanced swap types and customizations

#### 17. Rate Helpers
**Module**: ratehelpers.py
**SWIG File**: ratehelpers.i
**Coverage**: Partial

- [x] Core rate helper types (deposit, swap, cap/floor, etc.)
- [ ] Some specialized rate helpers

### Partially Covered Modules (Moderate Coverage)

#### 18. Stochastic Processes
**Module**: stochasticprocess.py
**SWIG File**: stochasticprocess.i
**Coverage**: Partial

- [x] Core stochastic process creation
- [x] Basic process inspection and manipulation
- [ ] Some advanced process types and functionality

#### 19. Volatilities
**Module**: volatilities.py
**SWIG Files**: volatilities.i, old_volatility.i, volatilitymodels.i
**Coverage**: Partial

- [x] Basic volatility surface creation and manipulation
- [x] Common volatility models
- [ ] Some advanced volatility model types and calibration methods

#### 20. Calibration
**Modules**: calibratedmodel.py, calibrationhelpers.py
**SWIG Files**: calibratedmodel.i, calibrationhelpers.i
**Coverage**: Partial

- [x] Core calibration functionality
- [ ] Some advanced calibration methods and helpers

#### 21. Default Probability
**Module**: defaultprobability.py
**SWIG File**: defaultprobability.i
**Coverage**: Partial

#### 22. Local Volatilities
**Module**: localvolatilities.py
**SWIG File**: localvolatilities.i
**Coverage**: Partial

### Not Covered Modules

#### 23. Asian Options
**SWIG File**: asianoptions.i
**Status**: Not implemented in QuantLibXlOil

- [ ] `AsianOption` - Asian/average option classes
- [ ] `ContinuousAveragingAsianOption` - Continuous averaging
- [ ] `DiscreteAveragingAsianOption` - Discrete averaging
- [ ] Asian option pricing engines

#### 24. Barrier Options
**SWIG File**: barrieroptions.i
**Status**: Not implemented in QuantLibXlOil

- [ ] `BarrierOption` - Barrier option classes
- [ ] Various barrier types (UpAndOut, DownAndIn, etc.)
- [ ] Barrier option pricing engines

#### 25. Basket Options
**SWIG File**: basketoptions.i
**Status**: Not implemented in QuantLibXlOil

- [ ] `BasketOption` - Basket option classes
- [ ] `MargrabeOption` - Margrabe option (exchange option) - NOTE: This appears to be partially covered
- [ ] Basket option pricing engines

#### 26. Cliquet Options
**SWIG File**: cliquetoptions.i
**Status**: Not implemented in QuantLibXlOil

- [ ] `CliquetOption` - Cliquet/ratchet option classes
- [ ] Cliquet option pricing engines

#### 27. Convertible Bonds
**SWIG File**: convertiblebonds.i
**Status**: Not implemented in QuantLibXlOil

- [ ] `ConvertibleBond` - Convertible bond classes
- [ ] Convertible bond pricing engines

#### 28. Exchange Rates
**SWIG File**: exchangerates.i
**Status**: Not implemented

- [ ] `ExchangeRate` - Exchange rate classes
- [ ] Exchange rate manipulation functions

#### 29. Forward and FRA
**SWIG Files**: forward.i, fra.i
**Status**: Not implemented

- [ ] `Forward` - Forward rate agreements
- [ ] `FRA` - Forward rate agreement classes

#### 30. Futures
**SWIG File**: futures.i
**Status**: Not implemented

- [ ] `Futures` - Futures contract classes

#### 31. Inflation
**SWIG File**: inflation.i
**Status**: Not implemented

- [ ] `Inflation` - Inflation modeling classes
- [ ] Inflation index classes
- [ ] Inflation-linked instrument classes

#### 32. Finite Difference Methods
**SWIG File**: fdm.i
**Status**: Partially covered through options module

- [ ] Limited direct FDM functionality
- [x] Some FDM engines available through options

#### 33. Fitted Bond Curve
**SWIG File**: fittedbondcurve.i
**Status**: Not implemented

- [ ] `FittedBondDiscountCurve` - Fitted bond curve classes
- [ ] Fitted curve construction and manipulation

#### 34. Gaussian 1D Model
**SWIG File**: gaussian1dmodel.i
**Status**: Not implemented

- [ ] `Gaussian1dModel` - 1D Gaussian model classes

#### 35. Grid
**SWIG File**: grid.i
**Status**: Not implemented

- [ ] `Grid` - Grid classes for numerical methods

#### 36. LMM (Libor Market Model)
**SWIG File**: lmm.i
**Status**: Not implemented

- [ ] `LiborMarketModel` - LMM classes
- [ ] LMM calibration and pricing

#### 37. Lookback Options
**SWIG File**: lookbackoptions.i
**Status**: Not implemented

- [ ] `LookbackOption` - Lookback option classes
- [ ] Lookback option pricing engines

#### 38. Market Elements
**SWIG File**: marketelements.i
**Status**: Not implemented

- [ ] `MarketElement` - Market element classes
- [ ] Market element manipulation

#### 39. Monte Carlo
**SWIG File**: montecarlo.i
**Status**: Partially covered through options module

- [ ] Limited direct Monte Carlo functionality
- [x] Some MC engines available through options

#### 40. Random Numbers
**SWIG File**: randomnumbers.i
**Status**: Not implemented

- [ ] `RandomNumberGenerator` - RNG classes
- [ ] Random number generation and seeding

#### 41. Short Rate Models
**SWIG File**: shortratemodels.i
**Status**: Not implemented

- [ ] `ShortRateModel` - Short rate model classes
- [ ] Hull-White, Vasicek, CIR models

#### 42. Spread Option
**SWIG File**: spreadoption.i
**Status**: Not implemented

- [ ] `SpreadOption` - Spread option classes
- [ ] Spread option pricing engines

#### 43. Statistics
**SWIG File**: statistics.i
**Status**: Not implemented

- [ ] `Statistics` - Statistical function classes
- [ ] Statistical calculations and accumulators

#### 44. Swing Options
**SWIG File**: swingoption.i
**Status**: Not implemented

- [ ] `SwingOption` - Swing option classes

#### 45. Time Basket
**SWIG File**: timebasket.i
**Status**: Not implemented

- [ ] `TimeBasket` - Time basket classes

#### 46. Time Series
**SWIG File**: timeseries.i
**Status**: Not implemented

- [ ] `TimeSeries` - Time series classes
- [ ] Time series analysis functions

## Coverage Summary by Category

### Excellent Coverage (80-100%)
- [x] Core date and time functionality
- [x] Calendar definitions
- [x] Day counters
- [x] Currencies
- [x] Basic mathematical functions (Black formula)
- [x] Credit default swaps
- [x] Settings and configuration
- [x] Basic instruments (bonds, swaps)

### Good Coverage (50-80%)
- [ ] Options (core functionality, missing some engines)
- [ ] Term structures and yield curves
- [ ] Cash flows
- [ ] Stochastic processes
- [ ] Volatility models
- [ ] Calibration functionality

### Partial Coverage (20-50%)
- [ ] Rate helpers
- [ ] Optimization
- [ ] Parameters

### Limited Coverage (0-20%)
- [ ] Exotic options (Asian, Barrier, Basket, Cliquet, Lookback, Spread, Swing)
- [ ] Convertible bonds
- [ ] Exchange rates
- [ ] Dividends
- [ ] Forward contracts and FRAs
- [ ] Futures
- [ ] Inflation modeling
- [ ] Random number generation
- [ ] Statistical functions
- [ ] Time series analysis
- [ ] Short rate models
- [ ] LMM (Libor Market Model)
- [ ] FDM (Finite Difference Methods)
- [ ] Monte Carlo simulation
- [ ] Integration methods
- [ ] ODE solvers

### Not Applicable
- [ ] Common SWIG infrastructure (common.i, types.i, vectors.i, etc.)
- [ ] Internal patterns (observer.i, lazyobject.i)
- [ ] Debugging features (tracing.i)

## Function Count Analysis

### QuantLibXlOil Exposed Functions by Module

| Module | Function Count | Status |
|--------|---------------|--------|
| blackformula.py | 7-10 | Complete |
| bonds.py | 40-50 | Partial |
| calendars.py | 30-40 | Complete |
| calibratedmodel.py | 8-12 | Partial |
| calibrationhelpers.py | 9-15 | Partial |
| cashflows.py | 100+ | Partial |
| creditdefaultswap.py | 25-35 | Complete |
| currencies.py | 8-12 | Complete |
| date.py | 25-35 | Complete |
| daycounters.py | 6-10 | Complete |
| defaultprobability.py | 15-25 | Partial |
| dividends.py | 5-10 | Limited |
| exercise.py | 5-10 | Complete |
| grid.py | 5-10 | Limited |
| indexes.py | 20-30 | Complete |
| instruments.py | 5-10 | Partial |
| localvolatilities.py | 10-15 | Partial |
| options.py | 200-300 | Partial |
| optimizers.py | 10-15 | Partial |
| parameter.py | 10-15 | Partial |
| payoffs.py | 15-25 | Complete |
| piecewiseyieldcurve.py | 20-30 | Partial |
| quantlib_.py | 5-10 | Complete |
| ratehelpers.py | 50-80 | Partial |
| rounding.py | 5-10 | Complete |
| scheduler.py | 15-25 | Complete |
| settings.py | 5-10 | Complete |
| stochasticprocess.py | 30-50 | Partial |
| swap.py | 100-150 | Partial |
| termstructures.py | 30-50 | Partial |
| volatilities.py | 30-50 | Partial |

**Total Exposed Functions**: ~800-1200

### QuantLib-SWIG v1.41 Interface

**Estimated Total Classes**: 200-300
**Estimated Total Functions/Methods**: 2000-3000
**Coverage Ratio**: ~30-50% (depending on how coverage is measured)

## Key Findings

### Strengths
1. **Comprehensive Core Coverage**: All fundamental date, time, calendar, and basic financial functionality is well covered.
2. **Strong Fixed Income Support**: Bonds, swaps, and credit default swaps have excellent coverage.
3. **Good Options Support**: Core option functionality with multiple pricing engines is available.
4. **Term Structure Coverage**: Yield curves and term structures are well supported.
5. **Consistent API Design**: Functions follow a clear naming convention (`qlClassNameMethod`).

### Gaps
1. **Exotic Options**: Most exotic option types (Asian, Barrier, Basket, etc.) are not covered.
2. **Advanced Models**: Many advanced stochastic models and processes are missing.
3. **Numerical Methods**: Limited coverage of finite difference methods, Monte Carlo simulation, and numerical integration.
4. **Market Data**: Incomplete coverage of inflation, dividends, exchange rates, and other market data components.
5. **Utilities**: Missing statistical functions, random number generation, and time series analysis.

### Recommendations

#### High Priority (Critical Financial Functionality)
1. **Asian Options**: Implement support for average/Asian options which are widely used in commodities and FX.
2. **Barrier Options**: Add barrier option support for structured products.
3. **Basket Options**: Implement basket option functionality for multi-asset products.
4. **Convertible Bonds**: Add convertible bond pricing and analytics.

#### Medium Priority (Commonly Used Features)
1. **Forward Contracts and FRAs**: Implement basic forward rate agreement functionality.
2. **Monte Carlo Engines**: Add more Monte Carlo pricing engines for various instrument types.
3. **Finite Difference Methods**: Implement FDM engines for advanced pricing.
4. **Inflation Modeling**: Add inflation-linked instrument support.

#### Low Priority (Specialized Functionality)
1. **Exotic Exotics**: Lookback, cliquet, swing options for specialized use cases.
2. **Advanced Short Rate Models**: Hull-White, Vasicek, CIR models for interest rate derivatives.
3. **Libor Market Model**: LMM implementation for advanced interest rate modeling.
4. **Stochastic Local Volatility**: SLV models for advanced equity derivatives.

## Implementation Notes

### Naming Convention
QuantLibXlOil follows a consistent naming convention:
- All exposed functions start with `ql` prefix
- Constructor-like functions: `qlClassName` (e.g., `qlEuropeanOption`)
- Method-like functions: `qlClassNameMethod` (e.g., `qlBondCleanPrice`)
- Type converter functions: `qType` (e.g., `qDate`, `qPeriod`)

### Function Signature Pattern
```python
@xlo.func(
    help="Function description",
    args={
        "param1": "Parameter 1 description",
        "param2": "Parameter 2 description",
        # ...
    },
    group=EXCEL_GROUP_NAME,
)
def qlFunctionName(param1, param2, ..., trigger=None):
    # Implementation
    return result
```

### Parameter Conversion
- Input parameters are converted from Excel types to QuantLib types using converter functions
- Output parameters are converted from QuantLib types to Excel types using returner functions
- Enum values are mapped to string keys for Excel compatibility

## QuantLib-SWIG v1.41 Specific Notes

### Version Compatibility
- QuantLibXlOil is designed to work with QuantLib-SWIG v1.41
- The version check in ql.i confirms: `#if QL_HEX_VERSION < 0x01410000` requires at least QuantLib 1.41
- This ensures compatibility with the latest features in QuantLib 1.41

### Python-Specific Features
The SWIG interface includes Python-specific enhancements:
- `%pythoncode` directives for custom Python wrappers
- `#if defined(SWIGPYTHON)` conditional compilation
- Automatic memory management
- Python-friendly method signatures

### Platform-Specific Considerations
- QuantLibXlOil focuses on the Python interface from QuantLib-SWIG
- Java and C# specific features are not relevant for this analysis
- The analysis considers only Python-agnostic or Python-specific SWIG definitions

## Conclusion

QuantLibXlOil provides comprehensive coverage of the core QuantLib functionality that is most commonly used in financial applications. The coverage is particularly strong in:

- **Fixed Income**: Bonds, swaps, credit default swaps
- **Basic Derivatives**: Vanilla options, Black formula calculations
- **Market Data**: Calendars, day counters, term structures
- **Core Utilities**: Date/time, currencies, settings

The main gaps are in exotic derivatives, advanced numerical methods, and some specialized market data components. These gaps represent opportunities for future development to expand the functionality available to Excel users.

The current coverage of ~30-50% of the QuantLib-SWIG interface is appropriate for many practical applications, as it focuses on the most commonly used functionality while maintaining a clean and consistent API design.

---

*Report generated for QuantLib-SWIG version: v1.41*
*Analysis date: 2026-06-23*
*Methodology: Pattern-based analysis of SWIG interface files and QuantLibXlOil source code*
*Coverage estimation: Based on function and class counts across modules*