## 8.4 Translation table of functional attributes to AFD2.0 attributes

In the consultation report, attribute names other than those in the final AFD 2.0 model were used in various places. Below is an overview of the functional attribute names and the final AFD 2.0 data names. The attributes of the cohort pool were discontinued in release 2027, because the cohort pool as a layer has been discontinued (#124); they are no longer included in the table.

<table>
<colgroup>
<col style="width: 19%" />
<col style="width: 13%" />
<col style="width: 21%" />
<col style="width: 45%" />
</colgroup>
<thead>
<tr>
<th><strong>Functional attribute name</strong></th>
<th><strong>AFD 2.0 entity.entitytype</strong></th>
<th><strong>AFD 2.0 attribute name</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<th>Transfer ID</th>
<td>commonTechnical.default</td>
<td>messageId</td>
<td>Unique message identification</td>
</tr>
<tr>
<th>Pensionfund ID</th>
<td>party.pensionProvider</td>
<td>puvCode</td>
<td>ID of the pension provider (PUV code) / Unique reference key assigned to an entity.</td>
</tr>
<tr>
<th>Pension scheme ID i</th>
<td>pension.scheme</td>
<td>refKey</td>
<td>ID of the pension scheme / (Unique reference key assigned to an entity.)</td>
</tr>
<tr>
<th>Capital i</th>
<td>pension.scheme</td>
<td>startAmount</td>
<td>Total pension assets as at the start date</td>
</tr>
<tr>
<th>Portfolio</th>
<td>pension.scheme</td>
<td>tradingPortfolioId</td>
<td>Portfolio ID of the custodian (safekeeping and management of financial assets)</td>
</tr>
<tr>
<th>Capital date i / Start date PUO admin / Start date Investment Report</th>
<td>financialInformation.reportingPeriod</td>
<td>startDate</td>
<td>Start date of the data period on which the delivery from the PUO is based, or reference date</td>
</tr>
<tr>
<th>End date PUO admin</th>
<td>financialInformation.reportingPeriod</td>
<td>endDate</td>
<td>End date of the data period on which the delivery from the PUO is based</td>
</tr>
<tr>
<th>Mutations date</th>
<td>financialInformation.reportingPeriod</td>
<td>mutationValuationDate</td>
<td>Date of processing of changes per age group</td>
</tr>
<tr>
<th>End date​ Investment Report</th>
<td>financialInformation.reportingPeriod</td>
<td>endDate</td>
<td>End date of the data period over which return is reported</td>
</tr>
<tr>
<th>Trade date</th>
<td>financialInformation.reportingPeriod</td>
<td>tradeDate</td>
<td>Requested trade date</td>
</tr>
<tr>
<th>Settlement date</th>
<td>financialInformation.reportingPeriod</td>
<td>investmentOrderSettlementDate</td>
<td>Date by which the full cycle of the investment order must have been settled</td>
</tr>
<tr>
<th>Projection date</th>
<td>financialInformation.reportingPeriod</td>
<td>projectionDate</td>
<td>Date of the projection of pension benefits</td>
</tr>
<tr>
<th>instruction date</th>
<td>financialInformation.reportingPeriod</td>
<td>instructionDate</td>
<td>Instruction date (date of the order sent by the PUO)</td>
</tr>
<tr>
<th>Estimation date</th>
<td>financialInformation.reportingPeriod</td>
<td>unitValueEstimationDate</td>
<td>Indicates the date on which the preliminary unit value (investment pool) was determined</td>
</tr>
<tr>
<th>Valuation date</th>
<td>financialInformation.reportingPeriod</td>
<td>participationValuationDate</td>
<td>Price date of the participation value (cohort pool)</td>
</tr>
<tr>
<th>value date</th>
<td>financialInformation.reportingPeriod</td>
<td>valueDate</td>
<td>Currency date.</td>
</tr>
<tr>
<th>Date</th>
<td>financialInformation.reportingPeriod</td>
<td>positionDate</td>
<td>The date on which the positions in the investment administration were established</td>
</tr>
<tr>
<th>Value</th>
<td>financialTransaction.payment</td>
<td>amount</td>
<td>Amount in currency</td>
</tr>
<tr>
<th>currency i</th>
<td>financialTransaction.payment</td>
<td>currencyType</td>
<td>Currency</td>
</tr>
<tr>
<th>IBAN debet i</th>
<td>financialTransaction.payment</td>
<td>collectionAccountIban</td>
<td>IBAN of the debit account</td>
</tr>
<tr>
<th>Description i</th>
<td>financialTransaction.payment</td>
<td>description</td>
<td>Description of the transaction (payment)</td>
</tr>
<tr>
<th>IBAN credit i</th>
<td>party.creditor</td>
<td>collectionAccountIban</td>
<td>IBAN of the credit account per scheme</td>
</tr>
<tr>
<th>Counterparty i</th>
<td>party.creditor</td>
<td>collectionAccountInNameOf</td>
<td>Name of the counterparty per scheme</td>
</tr>
<tr>
<th>BIC i</th>
<td>party.creditor</td>
<td>collectionAccountBic</td>
<td>Business Identifier Code (BIC) per scheme</td>
</tr>
<tr>
<th>BIC-correspondent i</th>
<td>party.creditor</td>
<td>collectionAccountBicCorrespondent</td>
<td>BIC correspondent per scheme</td>
</tr>
<tr>
<th>Contribution i</th>
<td>financialTransaction.cashflow</td>
<td>contributionAmount</td>
<td>Sum of contributions</td>
</tr>
<tr>
<th>Contribution date i</th>
<td>financialTransaction.cashflow</td>
<td>contributionDate</td>
<td>Date of receipt of the contribution</td>
</tr>
<tr>
<th>Withdrawal i</th>
<td>financialTransaction.cashflow</td>
<td>withdrawalAmount</td>
<td>Sum of the outflow</td>
</tr>
<tr>
<th>Withdrawal date i</th>
<td>financialTransaction.cashflow</td>
<td>withdrawalDate</td>
<td>Date on which (at the latest) the liquidity for the withdrawal has been released</td>
</tr>
<tr>
<th>Net contribution/withdrawal i</th>
<td>financialTransaction.cashflow</td>
<td>netAmount</td>
<td>Sum of contributions and withdrawals per scheme (net). A negative amount is a (net) withdrawal. / Difference between contribution and withdrawal. A negative amount is a (net) withdrawal.)</td>
</tr>
<tr>
<th>Net contribution/withdrawal<br />
date i</th>
<td>financialTransaction.cashflow</td>
<td>netDate</td>
<td>Date on which netted inflow and outflow is facilitated / Date on which the balance of contribution and withdrawal is determined</td>
</tr>
<tr>
<th>Cohort ID i, k</th>
<td>financialTransaction.payment</td>
<td>refKey</td>
<td>ID of the expected payment</td>
</tr>
<tr>
<th>Expected pension payment Date i, k</th>
<td>financialTransaction.payment</td>
<td>expectedPensionPaymentDate</td>
<td>Time of pension benefit payment</td>
</tr>
<tr>
<th>Hedged expected pension payment i,k</th>
<td>financialTransaction.payment</td>
<td>hedgedExpectedPensionPaymentAmount</td>
<td>Cash flow to be hedged across all cohorts</td>
</tr>
<tr>
<th>Cohort expected pension payment i,j,k</th>
<td>financialTransaction.payment</td>
<td>amount</td>
<td>Projected benefit across all cohorts</td>
</tr>
<tr>
<th>Cohort ID i, k</th>
<td>pension.cohort</td>
<td>refKey</td>
<td>ID of the cohort</td>
</tr>
<tr>
<th>Cohort Capital i,k</th>
<td>pension.cohort</td>
<td>startAmount</td>
<td>Pension assets of the cohort as at the start date</td>
</tr>
<tr>
<th>Net contribution/withdrawal I,k</th>
<td>pension.cohort</td>
<td>netAmount</td>
<td>Sum of contributions and withdrawals per cohort. A negative amount is a (net) withdrawal.)</td>
</tr>
<tr>
<th>Cohort contribution i,k</th>
<td>pension.cohort</td>
<td>contributionAmount</td>
<td>Inflow to be invested by the fiduciary manager</td>
</tr>
<tr>
<th>Cohort withdrawal i,k</th>
<td>pension.cohort</td>
<td>withdrawalAmount</td>
<td>Outflow to be invested by the fiduciary manager</td>
</tr>
<tr>
<th>Cohort return rate protection i,k</th>
<td>pension.cohort</td>
<td>protectionReturnPercentage</td>
<td>The protection return achieved, as a percentage, over the data period per scheme and per cohort</td>
</tr>
<tr>
<th>Cohort return rate excess i,k</th>
<td>pension.cohort</td>
<td>excessReturnPercentage</td>
<td>The excess return achieved, as a percentage, over the data period per scheme and per cohort</td>
</tr>
<tr>
<th>Cohort return protection i,k</th>
<td>pension.cohort</td>
<td>protectionReturnAmount</td>
<td>The protection return achieved, in the currency of the scheme, over the data period per scheme and per cohort</td>
</tr>
<tr>
<th>Cohort return excess i,k</th>
<td>pension.cohort</td>
<td>excessReturnAmount</td>
<td>The excess return achieved, in the currency of the scheme, over the data period per scheme and per cohort</td>
</tr>
<tr>
<th>Hedged expected pension payment i,k</th>
<td>financialTransaction.payment</td>
<td>hedgedExpectedPensionPaymentAmount</td>
<td>Cash flow to be hedged</td>
</tr>
<tr>
<th>Cohort expected pension payment i,j,k</th>
<td>financialTransaction.payment</td>
<td>amount</td>
<td>Projected benefit</td>
</tr>
<tr>
<th>Pool ID i,j</th>
<td>investment.pool</td>
<td>refKey</td>
<td>ID of the investment pool per scheme</td>
</tr>
<tr>
<th>Market value portfolio</th>
<td>investment.pool</td>
<td>marketValueAmount</td>
<td>Market value per portfolio per scheme in currencyType</td>
</tr>
<tr>
<th>Pool value i, k</th>
<td>investment.pool</td>
<td>unitsSummedValueAmount</td>
<td>Value per investment pool (unit value)</td>
</tr>
<tr>
<th>Market value instrument</th>
<td>investment.pool</td>
<td>marketValueAmount</td>
<td>Market value of the investment pool in currencyType of the pool</td>
</tr>
<tr>
<th>Preliminary market value i, k</th>
<td>investment.pool</td>
<td>preliminaryMarketValueAmount</td>
<td>Preliminary market value per portfolio per scheme in currencyType of the pool</td>
</tr>
<tr>
<th>Preliminary pool value i, k</th>
<td>investment.pool</td>
<td>preliminaryUnitValueAmount</td>
<td>Daily determined unit price/NAV in currencyType of the pool</td>
</tr>
<tr>
<th>number of units investment pool i,k</th>
<td>investment.pool</td>
<td>numberOfUnits</td>
<td>Number of units issued for the investment pool,</td>
</tr>
<tr>
<th>currency i,j</th>
<td>investment.pool</td>
<td>currencyType</td>
<td>Currency of the pool</td>
</tr>
<tr>
<th>Transaction description i,j, k /Description</th>
<td>investment.pool</td>
<td>description</td>
<td>Description</td>
</tr>
<tr>
<th>Dummy cash ID</th>
<td>investment.pool</td>
<td>dummyCashId</td>
<td>ID for dummy cash instrument per investment pool per scheme per cohort(pool)</td>
</tr>
<tr>
<th>Sell buy ID i,j, k</th>
<td>investment.pool</td>
<td>buySellId</td>
<td>Buy/sell indicator; ID for buy/sell per investment pool per scheme per cohort</td>
</tr>
<tr>
<th>Amount i,j, k</th>
<td>investment.pool</td>
<td>tradeQuantity</td>
<td>Number of pieces (units) to be traded in the transaction</td>
</tr>
<tr>
<th>Unit value i,j, k</th>
<td>investment.pool</td>
<td>unitPrice</td>
<td>Unit value (/price) per investment pool per scheme per cohort</td>
</tr>
<tr>
<th>FX rate i,j, k</th>
<td>investment.pool</td>
<td>currencyExchangeRate</td>
<td>FX rate per investment pool per scheme per cohort</td>
</tr>
<tr>
<th>Value i,k</th>
<td>investment.pool</td>
<td>tradeValueAmount</td>
<td>Transaction value per investment pool per scheme (summed over cohorts)</td>
</tr>
<tr>
<th>portfolio ID i,n</th>
<td>investment.portfolio</td>
<td>refKey</td>
<td>Investment portfolio ID / Unique reference key assigned to an entity.</td>
</tr>
<tr>
<th>Total Market Value start I,n</th>
<td>investment.portfolio</td>
<td>startAmount</td>
<td>The value of the Total Market Value at the start of the data period</td>
</tr>
<tr>
<th>Net contribution/withdrawal I, n</th>
<td>investment.portfolio</td>
<td>netAmount</td>
<td>Sum of contributions and withdrawals per scheme (net). A negative amount is a (net) withdrawal</td>
</tr>
<tr>
<th>Total Market Value end I,n</th>
<td>investment.portfolio</td>
<td>endAmount</td>
<td>The value of the Total Market Value at the end of the data period. Per scheme and investment portfolio</td>
</tr>
<tr>
<th>Return rate i,n​</th>
<td>investment.portfolio</td>
<td>returnPercentage</td>
<td>The return achieved, as a percentage, over the data period per scheme and per investment portfolio</td>
</tr>
<tr>
<th>Return i,n​</th>
<td>investment.portfolio</td>
<td>returnAmount</td>
<td>The return achieved, in the currency of the scheme, over the data period per scheme and per investment portfolio</td>
</tr>
<tr>
<th>Identifier</th>
<td>investment.investmentDetails</td>
<td>refKey</td>
<td>Identifier (for example ISIN or internal code)</td>
</tr>
<tr>
<th>Fund Name i</th>
<td>investment.investmentDetails</td>
<td>description</td>
<td>The name of the investment / the official name of the fund / of the instrument</td>
</tr>
<tr>
<th>Local Price i,j, k</th>
<td>investment.investmentDetails</td>
<td>currencyType</td>
<td>Currency of the instrument</td>
</tr>
<tr>
<th>Total holdings i,j, k</th>
<td>investment.investmentDetails</td>
<td>numberOfHoldings</td>
<td>Number of holdings per instrument per scheme per investment portfolio</td>
</tr>
<tr>
<th>Local Price i,j, k</th>
<td>investment.investmentDetails</td>
<td>localPrice</td>
<td>Price per instrument in original currency per scheme per investment portfolio</td>
</tr>
<tr>
<th>Local Value instrument i,j, k</th>
<td>investment.investmentDetails</td>
<td>localValueAmount</td>
<td>Total market value in original currency per instrument per scheme per investment portfolio[1]</td>
</tr>
<tr>
<th>Result i,j, k[1]</th>
<td>investment.investmentDetails</td>
<td>result</td>
<td>Unrealised result per instrument per scheme per investment portfolio</td>
</tr>
<tr>
<th>Accrued Interest i,j, k</th>
<td>investment.investmentDetails</td>
<td>accruedInterest</td>
<td>Accrued interest per instrument per scheme per investment portfolio</td>
</tr>
<tr>
<th>Portfolio weight i,j, k</th>
<td>investment.investmentDetails</td>
<td>poolPercentage</td>
<td>Weight in the portfolio per instrument per scheme per investment portfolio[2]</td>
</tr>
<tr>
<th>FX rate i,j, k</th>
<td>investment.investmentDetails</td>
<td>currencyExchangeRate</td>
<td>FX rates per instrument per scheme per investment portfolio / rate per positionDate</td>
</tr>
<tr>
<th>Trade date / Transaction date</th>
<td>financialTransaction.trade</td>
<td>tradeDate</td>
<td>Requested trade date</td>
</tr>
<tr>
<th>Adj Trade i, j</th>
<td>financialTransaction.trade</td>
<td>adjustmentIndicator</td>
<td>Adjusted trade instruction</td>
</tr>
<tr>
<th>Buy/Sell i,j</th>
<td>financialTransaction.trade</td>
<td>buySellId</td>
<td>Buy, sell, switch indicator</td>
</tr>
<tr>
<th>Amount</th>
<td>financialTransaction.trade</td>
<td>tradeAmount</td>
<td>Amount of the purchase in the currency in which the investment is denominated</td>
</tr>
<tr>
<th>Quantity</th>
<td>financialTransaction.trade</td>
<td>tradeQuantity</td>
<td>Number of pieces (units) to be traded in the transaction</td>
</tr>
<tr>
<th>Price i,j</th>
<td>financialTransaction.trade</td>
<td>tradePrice</td>
<td>Purchase price / rate</td>
</tr>
<tr>
<th>Switch type</th>
<td>financialTransaction.trade</td>
<td>switchType</td>
<td>Type of switch; one-day or sequential</td>
</tr>
<tr>
<th>Counterparty i,j</th>
<td>financialTransaction.trade</td>
<td>counterparty</td>
<td>Transfer Agent; the party that carries out the purchase/sale</td>
</tr>
<tr>
<th>Broker i,j</th>
<td>financialTransaction.trade</td>
<td>broker</td>
<td>Broker that executes investment orders on the market on behalf of clients</td>
</tr>
<tr>
<th>Interest i,j</th>
<td>financialTransaction.trade</td>
<td>interestAmount</td>
<td>Amount of applicable interest</td>
</tr>
<tr>
<th>Commission i, j</th>
<td>financialTransaction.trade</td>
<td>commissionAmount</td>
<td>Fee for executing the transaction</td>
</tr>
<tr>
<th>Clearing broker i,j</th>
<td>financialTransaction.trade</td>
<td>clearingBroker</td>
<td>Broker responsible for the administrative and financial settlement of the transaction</td>
</tr>
<tr>
<th>Cash account i,j</th>
<td>financialTransaction.trade</td>
<td>clearingBrokerCashAccount</td>
<td>Cash account (IBAN) with the clearing broker in the name of the pension provider</td>
</tr>
</tbody>
</table>

