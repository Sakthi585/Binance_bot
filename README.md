 Binance Futures Trading Bot (Python CLI)

A command-line trading bot for **Binance USDT-M Futures Testnet**, built in Python.  
The bot supports **market, limit, stop-limit, OCO, TWAP, and grid orders** with full validation and structured logging.


##  Features

###  Core Orders
- **Market Order**  
- **Limit Order**

###  Advanced Orders (Bonus)
- **Stop-Limit Order**  
- **OCO (One-Cancels-the-Other)**  
- **TWAP (Time-Weighted Average Price)**  
- **Grid Strategy**  

###  Validation
- Symbol format  
- Side (`BUY` / `SELL`)  
- Quantity  
- Price inputs (limit, stop, etc.)

###  Logging
All actions are saved in `bot.log` including:
- Order requests  
- Responses  
- Errors  
- Execution timestamps  

---

##  Project Structure

[project_root]/
│
├── src/
│ ├── market_orders.py
│ ├── limit_orders.py
│ ├── validators.py
│ ├── config.py
│ ├── client.py
│ ├── logger_config.py
│ └── advanced/
│ ├── stop_limit_orders.py
│ ├── oco.py
│ ├── twap.py
│ └── grid_strategy.py
│
├── bot.log
├── README.md
└── report.pdf (added during submission)

yaml
Copy code

---

## ⚙️ Setup Instructions
### 1️⃣ Clone the Repository
```bash
git clone <your_repo_url>
cd <repo_name>
2️⃣ Create a Virtual Environment
bash
Copy code
python -m venv venv
Activate it:

Windows:
bash
Copy code
venv\Scripts\Activate.ps1
3️⃣ Install Dependencies
bash
Copy code
pip install -r requirements.txt
4️⃣ Create a .env File
ini
Copy code
BINANCE_API_KEY=your_testnet_key
BINANCE_API_SECRET=your_testnet_secret
BINANCE_FUTURES_TESTNET=true
Use Binance Futures Testnet keys (not mainnet).

▶️ Usage (Run Orders)
Run all commands from the project root:

🟩 Market Order
bash
Copy code
python -m src.market_orders BTCUSDT BUY 0.001
🟦 Limit Order
bash
Copy code
python -m src.limit_orders BTCUSDT SELL 0.001 65000
🟧 Stop-Limit Order
bash
Copy code
python -m src.advanced.stop_limit_orders BTCUSDT BUY 0.001 64000 64500
🟥 OCO Order
bash
Copy code
python -m src.advanced.oco BTCUSDT BUY 0.001 68000 64000
🟨 TWAP Order
bash
Copy code
python -m src.advanced.twap BTCUSDT BUY 0.1 10 30
🟪 Grid Strategy
bash
Copy code
python -m src.advanced.grid_strategy BTCUSDT BUY 0.001 60000 70000 5
📊 Logging
All execution logs appear in:

lua
Copy code
bot.log
Each entry contains:

Timestamp

Module

Actions performed

Success / failure details

