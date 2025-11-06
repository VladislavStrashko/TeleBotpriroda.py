import telebot
import random
import os


print(os.listdir("images"))
bot = telebot. TeleBot("TOKEN")


@bot.message_handler (commands=["start", "hello"])
def send_welcome(message):
    bot. reply_to('message,f"Привет! бот (bot.get_me().first_name)!')

@bot. message_handler(commands=["facts"])
def send_time(message):
    time =[
        "Пластик разлагается от 100 - 200 лет"
        "Стекло разлагается от 1000 лет до 1 миллиона лет",
        "Бумага разлагается за 1-4месяца",
        "Пластиковая посуда разлагается за 500–1000 лет",
        "Фольга разлагается за 80–200 лет"
        ]

truth = random.choice(time)
bot.reply_to(message, f"разложения:\n\n{truth}")

@bot.message_handler(commands=["problem"])
def send_welcome(message):
    cleans = [
        "загрязнение атмосферы",
        "загрязнениеводы и почвы",
        "приводит к изменению климата",
        "ухудшение здоровья человека",
        "Выбросы парниковых газов, таких как \(СО_{2}\) метан, способствуют глобальному потеплению"
        ]
    
clean =random. choice(cleans)
bot. reply_to(message,f"проблемы загрязнения: \n\n{clean}")


bot.polling()
