    from telegram import Update
    from telegram.ext import Updater, CommandHandler, CallbackContext

    # إدخل هنا رمز الـ Token الخاص ببوتك
    TOKEN = http://t.me/seln77_bot

    def start(update: Update, context: CallbackContext) -> None:
        update.message.reply_text('مرحبًا بك في بوت الألعاب! استخدم /play لبدء اللعب.')

    def play(update: Update, context: CallbackContext) -> None:
        update.message.reply_text('لنلعب! ماذا تريد أن تفعل؟')

    def main():
        updater = Updater(TOKEN)

        # الحصول على الممرات
        dispatcher = updater.dispatcher
        
        # إضافة الأوامر
        dispatcher.add_handler(CommandHandler('start', start))
        dispatcher.add_handler(CommandHandler('play', play))

        updater.start_polling()
        updater.idle()

    if __name__ == '__main__':
        main()
    
