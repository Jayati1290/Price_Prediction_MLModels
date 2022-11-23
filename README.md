BigFish take-home

A product manager plans to run a “flash sale campaign” for new users for one day. Eligible users will see a sale icon on the side of the screen with a countdown timer attached. When tapped on the icon, the offer’s price and the content will be shown on an in-game pop-up window. If the user closes the popup and dismisses the warning message, both the pop-up and the offer icon vanish. That user has lost the opportunity to purchase a fantastic offer. The option is also lost if the timer expires without the user tapping on the icon.

In trying to optimise the monetisation performance, the product manager asked you to build a model that, using data within 7 days, predicts the optimal price for the flash sale for each new user. There are pre-designed sale offers at different prices, and the game will take the model output and show the offer closest to the predicted price.

You are given ~6 weeks of data (15th Dec - 24th Jan) immediately before the campaign, which will be run on 1 Feb. In the datasets are the following fields: 

FULLNAME	TYPE	DESCRIPTION
BFGUDID	STRING	unique BFG device ID; the user's first device they installed the game
ACTIVITY_DATE	DATE	partition field based on the date of user/device activity
PLAY_SECONDS	NUMERIC	the total valid play seconds for a user/device on the activity date
PLAY_SESSION_COUNT	NUMERIC	the number of valid play sessions for a user/device that have ended on the activity date
APP_STORE	STRING	platform where game is sold; for example 'itunes', 'google', 'amazon'
COUNTRY_CODE	STRING	ISO alpha 2 country code based on the IP address associated with the install; or, if missing, the country code provided by the SDK
PRODUCT	STRING	the sku for the IAP product
CURRENCY	STRING	the currency used for the transaction
GROSS_USD_AMOUNT	FLOAT	gross revenue in USD for the transaction
PRICE_TIER	FLOAT	the USD price for the bundle (i.e. normalized price)
DAY_SINCE_INSTALL	INTEGER	the number of days between the current and the day the user started to play
MAX_PRICE_TIER	FLOAT	the highest price tier the user purchased in the first 7 days
AVG_PRICE_TIER	FLOAT	the average price tier the user purchased in the first 7 days
Note: each row represents a unique user day, unless there is more than one purchase on that day, in which case the purchase data  (‘product’, ‘currency’, ‘gross_usd_amount’, ‘price_tier’) would be different but the rest of the columns are duplicates

You will build a model to predict the optimal offer price tier for each user (denoted by a unique “bfgudid”) in the test set. There are a few valid approaches, such as:
1.	Use all but the last purchase history as input to predict the price of the last purchase
2.	Use the single previous purchase history as input to predict the price of the next purchase
3.	Use all, up to nth purchase history to predict the price of the n+1 purchase
4.	Any other that achieves the same objective

You are expected to submit ONE OR FEW approach with the following:
•	Coding, including data cleaning, feature engineering, and modelling
•	Write-up on: 
o	Reasons behind your chosen approach
o	Any potential improvements or additional ideas

Note: Despite this complex project, this is not a Kaggle contest. Hence, we do NOT expect you to spend more than a couple hours on the entire exercise. There is no need for extensive feature engineering or model tuning. A basic model will help us get a sense of the approach and technique. You can discuss any potential improvements or other ideas in your write-up. The reasoning behind your decision, along with your other ideas, is what makes the difference. What is your strategy for approaching problems like this? Why did you choose your approach over the others? What other features could improve model accuracy? Are there additional data you would request? If you had four weeks on the project rather than a few hours, how would you use that time to improve your work?
![image](https://user-images.githubusercontent.com/97277567/203466970-9d4d8d4b-02b6-4223-9f62-24bcd6a57847.png)
