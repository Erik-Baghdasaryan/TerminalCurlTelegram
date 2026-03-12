# TerminalCurlTelegram
Sending messages with terminal by using a bot on telegram.

For experimented users i added the command as a file so you can just insert in your .bashrc.

The idea of this command is to save some important reminders, links or anything else on your telegram with terminal debian.

## Requirements
I used a WSL of debian and all i had to install is the command *curl*.

## Phase 1: The One-Time Setup
Before using this command you need a mailbox (the bot) and your "address" (your Chat ID).

Create a Bot:

Open Telegram and search for @BotFather.

Send /newbot, give it a name, and a username.

Copy the API Token it gives you (e.g., 123456:ABC-DEF1234ghIkl-zyx57W2v1u1).

Get Your Chat ID:

Search for some "@userinfobot" in Telegram and click start.

It will reply with your Id (a 9 or 10-digit number). Save this.

Activate the Bot:

Search for your newly created bot and click Start. (The bot cannot message you until you've started a chat with it).

Once you have your TOKEN and CHAT_ID, you can use these commands:

Open your .bashrc or .zshrc and add this alias to make it a one-word command (Also dont forget to replace token and chat_id by yours):

```Bash
alias tsave='f(){ curl -s -X POST "https://api.telegram.org/botYOUR_TOKEN_HERE/sendMessage" -d "chat_id=YOUR_CHAT_ID_HERE&text=$1"; }; f'
```
Reload with:

```Bash
source ~/.bashrc
```
Now you can just type:

tsave "https://example.com/useful-link"

or anything else

tsave "some text"
