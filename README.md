# Cheque Verification Bot

## Project Overview
This Telegram bot is designed to verify and process cheque information. It utilizes a variety of Python modules to manage data, interact with users, and perform core bot functionalities.

## Features
- Cheque verification and processing.
- Interactive Telegram bot interface.
- Extensive use of Python modules for modular bot operations.

## Prerequisites
- Python 3.x
- A set of Python libraries as listed in the `requirements.txt`.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/YernurSnowy/Cheque_Bot
   ```
2. Install the required Python packages:
   ```bash
   pip install -r requirements.txt
   ```

## Configuration
Update `config.py` to reflect your local settings:
- Replace `BROWSER`, `con`, `admin_id`, and `TOKEN` with your own values.
- Use `BROWSER="chrome"` when operating on Windows and `BROWSER="firefox"` on Linux.

## Database Setup
Prepare the MySQL database with the following commands:
```sql
create database cheque_bot;

create table if not exists cheques
(
    id          bigint auto_increment,
    user_id     int          null,
    cheque_json text         null,
    qr_url      varchar(500) null,
    verified    tinyint(1)   null,
    constraint cheques_pk
        unique (id)
);

create table if not exists users_data
(
    user_id  varchar(255) null,
    username varchar(255) null
);
```

## File Descriptions
- `main.py` & `main_a2.py`: Entry points for the bot's operations.
- `methods.py`, `keyboards.py`, `router.py`: Handle operations, user interactions, and routing.
- `entities.py`, `db_repo.py`: Manage database interactions and data structures.

## Usage
To start the bot, run:
```bash
python main.py
```
Adjust as necessary if using features from `main_a2.py`.
