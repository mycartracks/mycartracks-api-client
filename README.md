
# MyCarTracks API Client

Lite Python implementation of MyCarTracks API v2 (https://www.mycartracks.com/api-docs/index.html).

## API Credentials
To obtain API credentials, follow these instructions:
1. Create account: https://www.mycartracks.com/sign-up
2. API credentials in account settings: https://www.mycartracks.com/portal/settings#api



```python
## Sample usage

%env TZ=UTC

import sys
sys.path.append("./API_Client/")

from ApiClient import ApiClient

CLIENT_ID = "1rN1hEkMZAZJhqkJMeQdMyBZMnEhPYQn46ZVP8nWz6FEHNpx1c.mycartracks.com";
CLIENT_SECRET = "S4xyvMwWv7dvvMj2NBWRvN7WSQjTx8cE"

c = ApiClient(CLIENT_ID, CLIENT_SECRET);
c.request_access()

params = {
    "sort" : "id",
    "limit" : "1"
}
r = c.get("https://www.mycartracks.com/services/rest/v2/vehicles", params)

print("Total rows from API: {}".format(len(r)))
# print("Result: {}".format(r))

```

    env: TZ=UTC
    Requesting access_token...
    Success, access_token: 0c0033a0-f473-5704-b71c-3c6955cc3e50, expires_in: 3592
    Request, url: https://www.mycartracks.com/services/rest/v2/vehicles, params: {'sort': 'id', 'limit': '1'}
    Success, status_code: 200
    Total rows from API: 4
