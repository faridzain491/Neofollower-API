# NeoFollower SMM Panel • API Documentation 📣

**Official API Reference for [NeoFollower.com](https://neofollower.com)** — the premier SMM panel offering automated social media services.

🔗 **Visit our main site:** [https://neofollower.com](https://neofollower.com)

---

## 🧩 API Overview

- **Base URL:** `https://neofollower.com/panel/api/v1`
- **Method:** `POST`
- **Response Format:** `JSON`

| Parameter   | Description                                | Example                   |
|-------------|--------------------------------------------|---------------------------|
| `key`       | Your unique API key (found in dashboard)   | `ABC123XYZ`               |
| `action`    | The action to perform                      | `services`, `add`, `status`, `balance` |

---

## 📦 Endpoints

### 1. Fetch Services List (`action=services`)

**Request:**

```

POST [https://neofollower.com/panel/api/v1](https://neofollower.com/panel/api/v1)
Content-Type: application/x-www-form-urlencoded

key=YOUR\_API\_KEY
action=services

````

**Response:**

```json
[
  {
    "service": 1,
    "name": "Instagram Followers",
    "type": "Default",
    "category": "Instagram",
    "rate": "0.50",
    "min": "50",
    "max": "10000",
    "refill": true,
    "cancel": false
  }
]
````

---

### 2. Create New Order (`action=add`)

**Request:**

```
POST https://neofollower.com/panel/api/v1

key=YOUR_API_KEY
action=add
service=SERVICE_ID
link=https://instagram.com/yourprofile
quantity=1000
```

**Response:**

```json
{ "order": 12345 }
```

---

### 3. Check Order Status (`action=status`)

**Single Order Request:**

```
key=YOUR_API_KEY
action=status
order=12345
```

**Response:**

```json
{
  "charge": "4.50",
  "start_count": "200",
  "status": "Processing",
  "remains": "800",
  "currency": "USD"
}
```

**Multiple Orders Request:**

```
key=YOUR_API_KEY
action=status
orders=12345,12346,12347
```

---

### 4. Get Balance (`action=balance`)

**Request:**

```
key=YOUR_API_KEY
action=balance
```

**Response:**

```json
{ "balance": "47.85", "currency": "USD" }
```

---

## 🔒 Authentication & Security

* Use your **unique API key** from your dashboard.
* All requests must be sent via **POST**.
* Ensure your API calls use **HTTPS** for secure transmission.

---

## 🌟 Best Practices

* Always handle response types: `Processing`, `Completed`, `Partial`, `Error`.
* Monitor `start_count` and `remains` for order tracking.
* Use status check for bulk orders to reduce API load.

---

## 🚀 Quick Start Example (PHP)

```php
<?php
$api_url = 'https://neofollower.com/panel/api/v1';
$data = [
  'key'     => 'YOUR_API_KEY',
  'action'  => 'add',
  'service' => 1,
  'link'    => 'https://instagram.com/yourprofile',
  'quantity'=> 1000
];

$options = [
  'http' => [
    'header'  => "Content-type: application/x-www-form-urlencoded\r\n",
    'method'  => 'POST',
    'content' => http_build_query($data),
  ],
];
$context  = stream_context_create($options);
$result = file_get_contents($api_url, false, $context);
print_r(json_decode($result, true));
```

---

## 🔗 Useful Links

* 🌐 **Main Website:** [https://neofollower.com](https://neofollower.com)
* 📚 **Support & Docs:** [https://neofollower.com/knowledgebase](https://neofollower.com/knowledgebase)
* 📞 **Contact Us:** [https://neofollower.com/contact](https://neofollower.com/contact)

---


**Start integrating with NeoFollower today — automate your social media growth and scale your marketing campaigns like a pro.**

```

---
