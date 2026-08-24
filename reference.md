# Reference
## Stores
<details><summary><code>client.stores.<a href="src/leal/stores/client.py">list</a>() -> typing.List[ListStoresResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns every store the authenticated user has access to, including summary counts for locations, cards, customers, and posters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.stores.list()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.stores.<a href="src/leal/stores/client.py">get</a>(...) -> GetStoresResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns detailed information for a single store, including summary counts for its associated resources.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.stores.get(
    id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Store ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.stores.<a href="src/leal/stores/client.py">update</a>(...) -> UpdateStoresResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates the store's name or store_name. Use `store_name` for the public-facing name displayed to customers.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.stores import UpdateStoresRequestAccount

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.stores.update(
    id=1,
    account=UpdateStoresRequestAccount(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**id:** `int` — Store ID
    
</dd>
</dl>

<dl>
<dd>

**account:** `UpdateStoresRequestAccount` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Cards
<details><summary><code>client.cards.<a href="src/leal/cards/client.py">list</a>(...) -> typing.List[ListCardsResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns loyalty card templates for the specified store. By default, only
active (unarchived) cards are returned. Use the `scope` parameter to include
archived cards.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.cards.list(
    account_id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**scope:** `typing.Optional[str]` — Filter cards by archive status. Default: active only.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.cards.<a href="src/leal/cards/client.py">create</a>(...) -> CreateCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new loyalty stamp card template for the store. The card defines the
visual design (colours, icon, strip) and program rules (stamps required,
initial stamps).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.cards import CreateCardsRequestCard

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.cards.create(
    account_id=1,
    card=CreateCardsRequestCard(
        name="name",
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**card:** `CreateCardsRequestCard` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.cards.<a href="src/leal/cards/client.py">get</a>(...) -> GetCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single loyalty card template by ID, including reward and customer card counts.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.cards.get(
    account_id=1,
    id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Card ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.cards.<a href="src/leal/cards/client.py">update</a>(...) -> UpdateCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates an existing loyalty card template. Only the provided attributes are changed.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.cards import UpdateCardsRequestCard

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.cards.update(
    account_id=1,
    id=1,
    card=UpdateCardsRequestCard(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Card ID
    
</dd>
</dl>

<dl>
<dd>

**card:** `UpdateCardsRequestCard` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Customers
<details><summary><code>client.customers.<a href="src/leal/customers/client.py">list</a>(...) -> ListCustomersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a paginated list of customers for the store. Use the `search` parameter to filter
by name, email, phone, card code (barcode), or external reference ID. Alternatively, pass
`source` AND `external_id` together to perform an exact lookup by an external reference -
the response will contain at most one customer.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.customers.list(
    account_id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**search:** `typing.Optional[str]` — Search query to filter customers by name, email, phone, card code (barcode), or external reference ID
    
</dd>
</dl>

<dl>
<dd>

**source:** `typing.Optional[str]` — External system slug (e.g. `square`, `shopify`). When combined with `external_id`, performs an exact lookup.
    
</dd>
</dl>

<dl>
<dd>

**external_id:** `typing.Optional[str]` — External system's identifier for the customer. Must be combined with `source`.
    
</dd>
</dl>

<dl>
<dd>

**page:** `typing.Optional[int]` — Page number (defaults to 1)
    
</dd>
</dl>

<dl>
<dd>

**items:** `typing.Optional[int]` — Number of items per page
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.customers.<a href="src/leal/customers/client.py">create</a>(...) -> CreateCustomersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new customer for the store. Requires `first_name` and at least one of `email` or `phone`.
Optionally enroll the customer in a loyalty card by passing `card_id`, and trigger delivery of
card links (email/SMS) by passing `send_card_links`. When a card with initial stamps is assigned,
those stamps are automatically applied as a welcome bonus.

Pass `metadata` to attach arbitrary key/value data, and `external_references` to link the
customer to records in other systems (e.g. Square, Shopify). External references are upserted
by `(source, external_id)` so this endpoint is safe to call with the same references twice.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.customers import CreateCustomersRequestCustomer

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.customers.create(
    account_id=1,
    customer=CreateCustomersRequestCustomer(
        first_name="first_name",
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**customer:** `CreateCustomersRequestCustomer` 
    
</dd>
</dl>

<dl>
<dd>

**card_id:** `typing.Optional[int]` — Loyalty card ID to auto-enroll the customer in
    
</dd>
</dl>

<dl>
<dd>

**send_card_links:** `typing.Optional[bool]` — When true, sends the card links to the customer via email/SMS after enrollment. Note: even without this flag, the response includes `apple_wallet_url` and `google_wallet_url` in each customer card object so you can deliver them yourself.
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.customers.<a href="src/leal/customers/client.py">get</a>(...) -> GetCustomersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns detailed information about a single customer, including all of their
enrolled loyalty cards with stamp progress and wallet pass URLs (`apple_wallet_url`
and `google_wallet_url`) for each card. Also includes `metadata` and
`external_references` so you can sync state with external systems.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.customers.get(
    account_id=1,
    id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Customer ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.customers.<a href="src/leal/customers/client.py">update</a>(...) -> UpdateCustomersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates an existing customer's details. To add stamps or redeem rewards, use the
customer cards endpoints instead.

`metadata` is shallow-merged into the existing metadata. `external_references` are upserted
by `(source, external_id)` - to remove a reference, omit it from subsequent calls and use
a separate `DELETE` workflow (not yet exposed via API; manage in dashboard for now).
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.customers import UpdateCustomersRequestCustomer

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.customers.update(
    account_id=1,
    id=1,
    customer=UpdateCustomersRequestCustomer(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Customer ID
    
</dd>
</dl>

<dl>
<dd>

**customer:** `UpdateCustomersRequestCustomer` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Customer Cards
<details><summary><code>client.customer_cards.<a href="src/leal/customer_cards/client.py">list</a>(...) -> typing.List[ListCustomerCardsResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all loyalty cards enrolled for a specific customer, including stamp progress,
status, wallet pass installation state, and wallet pass URLs (`apple_wallet_url` and
`google_wallet_url`) that you can use to let customers add their loyalty card to
Apple Wallet or Google Wallet from your own app or website.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.customer_cards.list(
    account_id=1,
    customer_id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**customer_id:** `int` — Customer ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.customer_cards.<a href="src/leal/customer_cards/client.py">get</a>(...) -> GetCustomerCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns detailed information about a specific customer card, including stamp progress,
a list of rewards the customer has earned enough stamps to redeem, and wallet pass URLs
(`apple_wallet_url` and `google_wallet_url`) for adding the card to Apple Wallet or
Google Wallet.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.customer_cards.get(
    account_id=1,
    customer_id=1,
    id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**customer_id:** `int` — Customer ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Customer card ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.customer_cards.<a href="src/leal/customer_cards/client.py">redeem</a>(...) -> RedeemCustomerCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Redeems a reward for a customer, deducting the required stamps from their card.
The customer must have enough stamps on this card to cover the reward's cost.
Triggers wallet pass updates and push notifications.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.customer_cards.redeem(
    account_id=1,
    customer_id=1,
    id=1,
    reward_id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**customer_id:** `int` — Customer ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Customer card ID
    
</dd>
</dl>

<dl>
<dd>

**reward_id:** `int` — Reward ID to redeem
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.customer_cards.<a href="src/leal/customer_cards/client.py">stamp</a>(...) -> StampCustomerCardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Adds stamps to a customer's loyalty card. Triggers ledger entries, wallet pass updates,
and push notifications. Pass `skip_notifications` to stamp silently.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.customer_cards.stamp(
    account_id=1,
    customer_id=1,
    id=1,
    stamps=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**customer_id:** `int` — Customer ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Customer card ID
    
</dd>
</dl>

<dl>
<dd>

**stamps:** `int` — Number of stamps to add (e.g. 1, 3)
    
</dd>
</dl>

<dl>
<dd>

**skip_notifications:** `typing.Optional[bool]` — When true, stamp changes bypass notifications
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Locations
<details><summary><code>client.locations.<a href="src/leal/locations/client.py">list</a>(...) -> typing.List[ListLocationsResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns every physical location belonging to the specified store.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.locations.list(
    account_id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.locations.<a href="src/leal/locations/client.py">create</a>(...) -> CreateLocationsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new physical location for the store. The provided address is
automatically geocoded to latitude and longitude coordinates in the background.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.locations import CreateLocationsRequestLocation

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.locations.create(
    account_id=1,
    location=CreateLocationsRequestLocation(
        address="address",
        name="name",
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**location:** `CreateLocationsRequestLocation` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.locations.<a href="src/leal/locations/client.py">get</a>(...) -> GetLocationsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single location by ID.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.locations.get(
    account_id=1,
    id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Location ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.locations.<a href="src/leal/locations/client.py">delete</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently deletes a location. This action cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.locations.delete(
    account_id=1,
    id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Location ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.locations.<a href="src/leal/locations/client.py">update</a>(...) -> UpdateLocationsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates an existing location. If the address is changed, it will be re-geocoded automatically.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.locations import UpdateLocationsRequestLocation

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.locations.update(
    account_id=1,
    id=1,
    location=UpdateLocationsRequestLocation(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Parent store ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Location ID
    
</dd>
</dl>

<dl>
<dd>

**location:** `UpdateLocationsRequestLocation` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Posters
<details><summary><code>client.posters.<a href="src/leal/posters/client.py">list</a>(...) -> typing.List[ListPostersResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all posters for the store. Optionally filter by card or active status.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.posters.list(
    account_id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**card_id:** `typing.Optional[int]` — Filter posters belonging to a specific card
    
</dd>
</dl>

<dl>
<dd>

**active:** `typing.Optional[str]` — When present, return only active posters
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.posters.<a href="src/leal/posters/client.py">create</a>(...) -> CreatePostersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new printable QR code poster for customer signup. The poster will automatically
generate a unique public signup URL and QR code. The `card_id` is required on create to
associate the poster with a loyalty card.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.posters import CreatePostersRequestPoster

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.posters.create(
    account_id=1,
    poster=CreatePostersRequestPoster(
        card_id=1,
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**poster:** `CreatePostersRequestPoster` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.posters.<a href="src/leal/posters/client.py">get</a>(...) -> GetPostersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single poster by ID, including generated signup and display URLs.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.posters.get(
    account_id=1,
    id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Poster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.posters.<a href="src/leal/posters/client.py">delete</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently deletes a poster. The public signup URL will stop working.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.posters.delete(
    account_id=1,
    id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Poster ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.posters.<a href="src/leal/posters/client.py">update</a>(...) -> UpdatePostersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates an existing poster. The `card_id` cannot be changed after creation.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.posters import UpdatePostersRequestPoster

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.posters.update(
    account_id=1,
    id=1,
    poster=UpdatePostersRequestPoster(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Poster ID
    
</dd>
</dl>

<dl>
<dd>

**poster:** `UpdatePostersRequestPoster` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Rewards
<details><summary><code>client.rewards.<a href="src/leal/rewards/client.py">list</a>(...) -> typing.List[ListRewardsResponseItem]</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns all rewards for the store. Optionally filter by card or active status.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.rewards.list(
    account_id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**card_id:** `typing.Optional[int]` — Filter rewards belonging to a specific card
    
</dd>
</dl>

<dl>
<dd>

**active:** `typing.Optional[str]` — When present, return only active rewards
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.rewards.<a href="src/leal/rewards/client.py">create</a>(...) -> CreateRewardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a new reward for a loyalty card. The card must belong to the same store.
The `card_id` is required on create but cannot be changed afterwards.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.rewards import CreateRewardsRequestReward

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.rewards.create(
    account_id=1,
    reward=CreateRewardsRequestReward(
        card_id=1,
        name="name",
        stamps_required=1,
    ),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**reward:** `CreateRewardsRequestReward` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.rewards.<a href="src/leal/rewards/client.py">get</a>(...) -> GetRewardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns a single reward by ID.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.rewards.get(
    account_id=1,
    id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Reward ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.rewards.<a href="src/leal/rewards/client.py">delete</a>(...)</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently deletes a reward. This cannot be undone.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.rewards.delete(
    account_id=1,
    id=1,
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Reward ID
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.rewards.<a href="src/leal/rewards/client.py">update</a>(...) -> UpdateRewardsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Updates an existing reward. The `card_id` cannot be changed after creation.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment
from leal.rewards import UpdateRewardsRequestReward

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.rewards.update(
    account_id=1,
    id=1,
    reward=UpdateRewardsRequestReward(),
)

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**account_id:** `int` — Store (account) ID
    
</dd>
</dl>

<dl>
<dd>

**id:** `int` — Reward ID
    
</dd>
</dl>

<dl>
<dd>

**reward:** `UpdateRewardsRequestReward` 
    
</dd>
</dl>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Status
<details><summary><code>client.status.<a href="src/leal/status/client.py">check</a>() -> CheckStatusResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Returns the status of the API. No authentication required.

Every response from this API, including this one, carries `RateLimit-Limit`,
`RateLimit-Remaining`, `RateLimit-Reset` and `RateLimit-Policy`. Exceeding
the limit returns 429 with `Retry-After` in seconds.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```python
from leal import Leal
from leal.environment import LealEnvironment

client = Leal(
    token="<token>",
    environment=LealEnvironment.PRODUCTION,
)

client.status.check()

```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request_options:** `typing.Optional[RequestOptions]` — Request-specific configuration.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

