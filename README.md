# Return Calculation

There are two types of returns calculated during calibration depending on whether the risk factor is an absolute risk factor or relative risk factor.  In addition, certain types of commodity risk factors require special treatment near the time of contract expiry - a process referred to as roll-over adjustment.  

Absolute returns are calculated as:

 

It is worth noting that for pipeline spreads, rather than calculating the spread followed by the spread’s return, the calculation is done in one step:

 

Relative returns are calculated as:

 

For pipeline all-in prices, any return that falls on the day of contract expiry is set to null.  This rule is only applied to the 1 month maturity contract.

For pipeline implied volatilities, any return that falls on a date beyond the 16th day of the contract is set to null.  This rule is only applied to the 1 month maturity contract.

For pipeline spreads, any return that falls on a date between expiry of the NG future contract and expiry of the pipeline forward contract is set to null.  This rule is applied to all contract maturities.

This is a place holder for a returns cleaning module.  Currently, the raw returns calculated from cleaned price series are simply copied to a new spreadsheet.

As with the price cleaning, prior to the inclusion of robust statistics into the calibration process, cleaning of the returns was required prior to actual calibration. With the inclusion of robust statistics, the cleaning of returns is no longer required; however the subsequent calibration steps still expect returns to be written. Therefore, the Returns Cleansing module simply copies the original raw returns and re-labels them as clean returns.

All risk factors are either simulated as relative (REL) returns or absolute (ABS) returns.  

For a portfolio containing absolute return risk factors, changes in the portfolio value are approximated by the following Taylor series expansion

 

For a portfolio containing relative return risk factors, changes in the portfolio value are approximated by the following Taylor series expansion

 

For relative return risk factors, the reported sensitivities (partial derivatives) are multiplied by the corresponding closing rate. 

Reference:

https://finpricing.com/FinPricing-ProductBrochure.pdf


