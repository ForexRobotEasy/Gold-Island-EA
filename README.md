# Gold Island EA ReadMe

## Description

Gold Island EA is an Expert Advisor (EA) developed by the Forex Robot Easy Team for automated Forex trading. It is designed to implement a risk management feature, adjust trade sizes based on risk levels, and apply the Martingale strategy. This EA aims to provide secure and low drawdown trading.

For detailed reviews and trading results of this product, please visit [Forex Robot Easy - Gold Island EA Review](https://forexroboteasy.com/forex-robot-review/gold-island-ea-review-secure-low-drawdown-forex-software/).

## Developer

This code is developed by the Forex Robot Easy Team. Please note that ForexRobotEasy is not the official developer of this product. We are showcasing this sample code to demonstrate how it can work based on the product's description. To find the official developer of this product, please refer to MQL5.

## Risk Management

The EA includes a risk management feature that allows you to adjust the risk level as a percentage of the total balance. By default, the risk level is set to 1% of the total balance. You can modify the `riskPercentage` variable to customize the risk level.

## Take Profit

The EA uses a take profit strategy to close trades at a specific profit level. The default take profit is set to 100 points. You can adjust the `takeProfit` variable to set your desired take profit level.

## Martingale Strategy

The Martingale strategy is implemented in this EA to adjust the trade size based on previous wins or losses. The `martingaleMultiplier` variable determines the multiplier for increasing the trade size after a loss, while the `martingaleDivisor` variable determines the divisor for decreasing the trade size after a win.

## Trading Logic

The EA uses the `OnTick()` and `OnTrade()` functions to execute its trading logic.

In the `OnTick()` function:
- The current account balance is retrieved using `AccountInfoDouble(ACCOUNT_BALANCE)`.
- The risk amount is calculated based on the risk percentage and the account balance.
- The trade size is calculated based on the risk amount, trade tick value, and trade contract size.
- If the trade size is greater than zero, a market order is placed using `OrderSend()`.
- The take profit level is calculated based on the trade size and take profit points, and then set for the order using `OrderTakeProfit()`.

In the `OnTrade()` function:
- It checks if there are any open orders using `OrdersTotal()`.
- If there are open orders, it retrieves the last order using `OrderSelect()` and determines its type using `OrderType()`.
- If the last order was a loss, the trade size for the next order is increased using the Martingale multiplier.
- If the last order was a win, the trade size for the next order is decreased using the Martingale divisor.

Please note that this is a simplified explanation of the code's functionality. For more details, it is recommended to refer to the official documentation or contact the official developer.

## Resources

To find the official developer of this product and obtain more information, please visit the developer's website: [Forex Robot Easy](https://forexroboteasy.com).

For detailed reviews and trading results of this product, please visit [Forex Robot Easy - Gold Island EA Review](https://forexroboteasy.com/forex-robot-review/gold-island-ea-review-secure-low-drawdown-forex-software/).
