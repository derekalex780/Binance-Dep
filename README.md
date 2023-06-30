from binance.client import Client

# Replace with your own API key and secret
API_KEY = 'your_api_key'
API_SECRET = 'your_api_secret'

# Create a Binance client
client = Client(API_KEY, API_SECRET)

# Fetch deposit address for a specific asset
asset = 'BTC'  # Replace with the desired asset symbol
address_info = client.get_deposit_address(asset=asset)

if address_info['success']:
    deposit_address = address_info['address']
    print(f"Deposit address for {asset}: {deposit_address}")

    # Perform a deposit to the fetched address
    amount = 0.1  # Replace with the desired deposit amount
    result = client.withdraw(
        asset=asset,
        address=deposit_address,
        amount=amount
    )

    if 'id' in result:
        print(f"Deposit successful. Transaction ID: {result['id']}")
    else:
        print("Deposit failed.")
else:
    print(f"Failed to fetch deposit address for {asset}")
