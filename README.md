A simple demo of applying fundamentals for stock selection

See [demo notebook](basepred.ipynb)

# Datasets

## SimFin

[SimFin](https://simfin.com/) dataset is used for analysis. It contains:
- Daily stock prices and dividends (dividends column is not empty for payment dates)
- Trailing Twelve Months (TTM) financial statements and financial ratios, where figures are calculated by summing four trailing quaterly reports are available
- Daily figures for price-dependent financial ratios

## pystock-data

`pystock-data` ([github](https://github.com/eliangcs/pystock-data)) can be used as an alternative dataset, but additional pre-processing steps are required. The data is available for US companies for 2009-2017 years. The data is stored in archive files inside the GitHub repo.

To calculate daily price-dependent ratios, like price to earnings, trailing twelve months (TTM) financial ratios like earnings can be calculated from the 10-Q / 10-K company reports. Then, daily price-dependent ratios can be calculated using the latest available TTM value.

`pystock-crawler` ([github](https://github.com/eliangcs/pystock-crawler)) CLI tool was used to crawl fundamentals from 10-Q and 10-K filings (XBRL) on SEC EDGAR and daily prices from Yahoo Finance. Dividend data from Yahoo Finance is not included, dividends from 10-Q and 10-K filings are included. An alternative way to abtain dvidends is to redownload daily stock prices using `yfinance` ([github](https://github.com/ranaroussi/yfinance)), since it downloads dividend history column.
