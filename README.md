# WalletManager

This application uses
1. Java17
2. h2 database
3. Docker
4. Spring boot

ASUUMPTION
1. Already have accounts/players ids in account_details table.
2. Caller sending transactionId used for checking if transaction already exists or not

BUILD
1. mvn clean install
2. docker build --tag=wallet-manager:latest .


RUN
1. docker run -p 8080:8080 wallet-manager

# Register Transaction

curl --location --request POST 'http://localhost:8080/transaction/register' \
--header 'Content-Type: application/json' \
--data-raw '{
    "transactionId" : 125592556,
    "amount": "1021.898",
    "transactionType" : "CREDIT",
    "accountId": 124
}'

# Get List of Transaction History

curl --location --request GET 'http://localhost:8080/transaction/history?accountId=124'
