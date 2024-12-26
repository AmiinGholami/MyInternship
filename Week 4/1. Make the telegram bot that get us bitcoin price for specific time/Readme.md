# **Project Report: Bitcoin Price Telegram Bot**

## **Introduction**
This report documents the development of a Telegram bot named **AmiinBitcoinPriceBot**. The bot retrieves the price of Bitcoin for a specific date using the **yFinance library** and interacts with users via Telegram's bot platform.

---

## **Objectives**
The primary goal was to create a bot that:
1. Allows users to input a specific date.
2. Fetches and displays the closing price of Bitcoin (in USD) for the given date.
3. Provides an easy-to-use interface via Telegram.

---

## **Development Process**

### **1. Bot Creation in Telegram**
1. The bot was registered using **BotFather** in Telegram.
2. The following command sequence was used:
   - `/start` to initiate BotFather.
   - `/newbot` to create a new bot.
3. The bot was given the name **Bitcoin Price Tracker** and the username **AmiinBitcoinPriceBot**.
4. A unique **access token** was generated for the bot.

---

### **2. Environment Setup**
1. Python was chosen as the programming language due to its extensive libraries and ease of integration.
2. The following Python libraries were installed:
   ```bash
   pip install pyTelegramBotAPI yfinance
3.	The development environment was configured on a local machine.

3. Implementation

## The implementation was divided into distinct steps:

### Bot Initialization

The bot was initialized using the telebot library with the token provided by BotFather:

``` TOKEN = 'your-telegram-bot-token'
bot = telebot.TeleBot(TOKEN)
```

## Fetching Bitcoin Price

The yFinance library was used to retrieve historical Bitcoin prices:

```
def get_bitcoin_price(date):
    btc = yf.Ticker("BTC-USD")
    historical = btc.history(start=date, end=date)
    price = historical['Close'].iloc[0]
    return f"Bitcoin price on {date} was ${price:.2f}"
```

## Handling User Commands

The bot was programmed to handle the /price command and user-provided dates:

```
@bot.message_handler(commands=['price'])
def send_welcome(message):
    bot.reply_to(message, "Please enter the date in YYYY-MM-DD format:")

@bot.message_handler(func=lambda message: True)
def fetch_price(message):
    date = message.text.strip()
    try:
        datetime.strptime(date, '%Y-%m-%d')  # Validate date format
        price_message = get_bitcoin_price(date)
        bot.reply_to(message, price_message)
    except ValueError:
        bot.reply_to(message, "Invalid date format. Please use YYYY-MM-DD.")
```

## Running the Bot

The bot was activated using the following script:

```
print("Bot is running...")
bot.polling()
```

## 4. Testing
	1.	The bot was tested in Telegram by sending the /price command.
	2.	Various dates were inputted, and the bot successfully fetched Bitcoin prices.
	3.	Invalid inputs (e.g., incorrect date format) were handled gracefully.

## Results
	•	The bot, AmiinBitcoinPriceBot, is fully operational and responds accurately to user requests.
	•	It provides the closing price of Bitcoin for any valid date input in the YYYY-MM-DD format.

## Challenges and Resolutions
	1.	Date Validation
	•	Challenge: Ensuring the input date format is correct.
	•	Resolution: Used Python’s datetime.strptime for validation.
	2.	Data Retrieval for Non-Trading Days
	•	Challenge: Some dates (e.g., weekends) had no trading data.
	•	Resolution: Instructed users to select valid trading dates.
	3.	API Response Time
	•	Challenge: Occasionally, the API took longer than expected to respond.
	•	Resolution: Implemented a user-friendly error message.

## Future Improvements
	1.	Deploy the bot on a cloud server (e.g., Heroku or AWS) for 24/7 availability.
	2.	Add functionality for live Bitcoin price tracking.
	3.	Implement multi-language support for a broader audience.
	4.	Enhance error handling for API issues.

## Conclusion

The AmiinBitcoinPriceBot successfully fulfills its purpose of providing historical Bitcoin prices. Its user-friendly interaction and reliable data fetching make it a valuable tool for cryptocurrency enthusiasts.

For further development or inquiries, feel free to contact me!