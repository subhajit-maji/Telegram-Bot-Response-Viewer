# Telegram Response Viewer Bot (PHP)

This is a simple yet powerful Telegram bot script written in PHP. Its primary function is to handle new member registrations for a gaming guild (e.g., Free Fire). The bot collects information from users step-by-step and forwards it directly to the admin's Telegram ID.

## ✨ Main Features

* **Step-by-Step Registration (Multi-Step Form):** Collects information from users in a step-by-step manner through a conversation.
 * **Admin Notifications**:** Upon completion of a new registration, the admin immediately receives a message with complete user information.
* **Admin Panel**:** A web-based admin dashboard where you can view bot statistics, such as total users, active registrations, and recent activity.
* **No Database Required**:** This bot stores user data and logs in `.json` files on the server itself, so you don't need an external database like MySQL.
* **Easy Setup**:** The bot is very easy to configure and run on the server.
* **Customizable**:** You can easily customize the registration questions to suit your needs.

 ## ⚙️ Installation & Setup

Follow the steps below to set up the bot:

1. **Download Files**:**
Download all the files from this repository and upload them to your web hosting (cPanel or any other) where PHP runs.

2. **Edit Configuration**:**
Edit the `config.php` file and fill in your details:
* `YOUR_BOT_TOKEN_HERE`: Enter your Telegram bot token here, which you will receive from BotFather.
* `YOUR_ADMIN_TELEGRAM_ID_HERE`: Enter your Telegram user ID here, to which you want to receive registration information.

3. **Set Webhook**:**
Open the `setup.php` file in your browser.  Example: `https://yourdomain.com/path/to/files/setup.php`
This script will automatically set up a webhook for your bot.

* **Security Warning:** After setup is complete, delete or rename the `setup.php` file from your server for security reasons.

4. **Change Admin Password:**
Open the `admin.php` file and change the default password to `SM` for security reasons.

Your bot is now ready to use!

## ✏️ How to Customize Questions

You can easily customize the questions asked to users as per your convenience. All questions are located in the `index.php` file.

For example, if you want to ask for "Game ID" instead of "FF UID":

* Open the `index.php` file.

 * In the `startGuildForm` function, find the line `sendMessage($chatId, 'Please enter your FF UID...');`.

* In this line, replace the text `Please enter your FF UID...'` with a question of your choice, such as `Please enter your Game ID...'`.

Similarly, you can change the question text in all functions like `handleFFUIDStep`, `handleBermudaRankStep`.

## 📂 File Structure (Project Files)

* `index.php`: The bot's main logic, which handles messages and commands.
* `admin.php`: The web-based admin panel.
* `config.php`: All configuration, such as the bot token and admin ID.
* `setup.php`: The script for setting up the webhook.

 * `database.php`: Class for managing file-based data.

* `/data/` & `/logs/`: These directories are automatically created to store user data and logs.