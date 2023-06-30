Before running the code, make sure to replace 'your_api_key' and 'your_api_secret' with your actual Binance API key and secret. Additionally, set the asset variable to the desired asset symbol (e.g., 'BTC', 'ETH', etc.), and adjust the amount variable according to the desired deposit amount.

Please note that this is just a basic example, and you may need to handle additional error cases, implement proper error handling, and ensure you have sufficient account balance for the deposit, among other considerations. Also, make sure to install the python-binance library using pip before running the code: pip install python-binance.

    if 'id' in result:
        print(f"Deposit successful. Transaction ID: {result['id']}")
    else:
        print("Deposit failed.")
else:
    print(f"Failed to fetch deposit address for {asset}")
