---
title: 'Decenteralized Finance Calender Versioning'
---

DeFiVer
===
![downloads](https://img.shields.io/github/downloads/atom/atom/total.svg)
![build](https://img.shields.io/appveyor/ci/:user/:repo.svg)
![chat](https://img.shields.io/discord/:serverId.svg)

[TOC]

# 

## 30/360 Methods
###### tags: 30/360 Bond Basis

The conventions are distinguished by the manner in which they adjust Date1 and/or Date2 for the end of the month. Each convention has a set of rules directing the adjustments.

Treating a month as 30 days and a year as 360 days was devised for its ease of calculation by hand compared with manually calculating the actual days between two dates. Also, because 360 is highly factorable, payment frequencies of semi-annual and quarterly and monthly will be 180, 90, and 30 days of a 360-day year, meaning the payment amount will not change between payment periods.

All conventions of this class calculate the Factor as:

### Day count Factor

$$
\frac{360 \times\left(Y_{2}-Y_{1}\right)+30 \times\left(M_{2}-M_{1}\right)+\left(D_{2}-D_{1}\right)}{360}
$$

### Coupon count Factor

$$
\frac{360 \times\left(Y_{3}-Y_{1}\right)+30 \times\left(M_{3}-M_{1}\right)+\left(D_{3}-D_{1}\right)}{360}
$$

### Coupon 

This is the same as the Factor calculation, with Date2 replaced by Date3. In the case that it is a regular coupon period, this is equivalent to:


  
  
[30/360 Bond Basis](/-6dyCTK5ScaJyMhtgVtSww)  
  This convention is exactly as 30U/360 below, except for the first two rules. Note that the order of calculations is important:

-   D1 = MIN (D1, 30).
-   If D1 = 30 Then D2 = MIN (D2,30)

Other names:

-   30A/360.


---


## Day Count Convention

###
### Interest

Amount of interest accrued on an investment.

### CouponFactor

The Factor to be used when determining the amount of interest paid by the issuer on coupon payment dates. The periods may be regular or irregular.

### CouponRate

The interest rate on the security or loan-type agreement, e.g., 5.25%. In the formulas this would be expressed as 0.0525.

### Date1 (Y1.M1.D1)

Starting date for the accrual. It is usually the coupon payment date preceding Date2.

### Date2 (Y2.M2.D2)

Date through which interest is being accrued. You could word this as the "to" date, with Date1 as the "from" date. For a bond trade, it is the settlement date of the trade.

### Date3 (Y3.M3.D3)

Is the coupon payment date, usually it is close to Date2. This would be the maturity date if there are no more interim payments to be made.

### Days(StartDate, EndDate)

Function returning the number of days between StartDate and EndDate on a Julian basis (i.e., all days are counted). For instance, Days(15 October 2007, 15 November 2007) returns 31.

### EOM

Indicates that the investment always pays interest on the last day of the month. If the investment is not EOM, it will always pay on the same day of the month (e.g., the 10th).

### DayCountFactor

Figure representing the amount of the CouponRate to apply in calculating Interest. It is often expressed as "days in the accrual period / days in the year". If Date2 is a coupon payment date, Factor is zero.

### Freq

The coupon payment frequency. 1 = annual, 2 = semi-annual, 4 = quarterly, 12 = monthly, etc.

### Principal

Par value of the investment. (Also known as "face value", "nominal value" or just "par")
