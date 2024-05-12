!pip install python-telegram-bot

from telegram.ext import Updater, CommandHandler

# Bot Tokenini buraya yapıştırın
TOKEN = "6984630009:AAHEE-d3MFlevKk1vdfSx8PNnoYUOxPcgPc"

# Başlangıç komutu işlevi
def start(update, context):
    context.bot.send_message(chat_id=update.effective_chat.id, text="Merhaba! Ben Kenan İmirzalıoğlu botuyum.")

def main():
    updater = Updater(token=TOKEN, use_context=True)
    dispatcher = updater.dispatcher

    # Başlangıç komutunu tanımlayın ve bağlayın
    start_handler = CommandHandler('start', start)
    dispatcher.add_handler(start_handler)

    # Botu başlatın
    updater.start_polling()
    updater.idle()

if __name__ == '__main__':
    main()
