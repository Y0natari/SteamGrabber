# Steam Grabber

Do you have multiple Steam accounts and want to fetch various details from them without hassle? This lib provides a straightforward way to interact with Steam's interfaces and retrieve detailed information.

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install Steam Grabber.

```bash
pip install steam_grabber
```

## Usage

```python
import asyncio
import steam_grabber

async def main():
    webapi_key = '<YOUR_WEB_API_KEY>'
    client = steam_grabber.Client('<STEAM_LOGIN>', '<STEAM_PASSWORD>')
    await client.do_login()
    if client.logged_in:
        print(await client.get_all_account_info(webapi_key))
        await client.session.close()
    else:
        print("Login failed!")

asyncio.run(main())
```

## Supported methods 

**get_all_account_info:** Retrieve all account info

**get_balance():** Retrieve account's balance.

**get_currency():** Fetch account's currency.

**get_country():** Determine the account's country.

**get_steamid():** Get the account's Steam ID.

**get_email():** Obtain the associated email address.

**get_time_created(apikey: str)**: Get account's creation date.

**get_last_online(apikey: str):** Determine when the account was last online.

**get_vac_bans():** Retrieve any VAC bans

**get_games(apikey: str):** List of games owned by the account along with the playtime.

**get_games_count(apikey: str):** Get the number of games owned by the account.

##### **Please note that certain functions require an API key. Ensure you have a valid Steam API key before using them.**

## License

[MIT](https://choosealicense.com/licenses/mit/)
