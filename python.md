# Python Cheat-Sheet

## Terminal Commands

- aws configure [--profile profile-name]
  - enter the id key and secret key for the cli-accessing AWS account
- Compress-Archive -Path csv-to-json.py -CompressionLevel Optimal -DestinationPath function.zip
  - zip up lambda function for upload to AWS (powershell, not command prompt)
- aws lambda update-function-code --function-name csv_to_json --zip-file fileb://function.zip
  - updates an existing lamba in AWS
- pip --version
- pip install pandas
- pandas --version