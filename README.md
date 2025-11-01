import telebot

# Замени 'TOKEN' на токен вашего бота
bot = telebot.TeleBot('76258756A9FQK91uGhJU1q30T3P8')

@bot.message_handler(commands=['hello'])
def send_welcome(message):
    bot.reply_to(message, "Привіт! Я твій Telegram бот!")

@bot.message_handler(commands=['bye'])
def send_bye(message):
    bot.reply_to(message, "Пока! Удачи!")

@bot.message_handler(commands=['"passw"'])
def echo_all(message):
    bot.reply_to(message, message.text)

bot.polling()
