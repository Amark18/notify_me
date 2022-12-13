## Notify Mi
🔔 Notify Mi simplifies sending yourself text and email notifications from your personal projects by utilizing your gmail account. It is a convenient and cost-effective solution with the goal of providing you an `easy` and `free` way to send messages in response to events.

Notify Mi is particularly useful when working with IoT devices. It can allow you to receive messages in response to events such as when a sensor value reaches a certain threshold, when a sensor detects something, when a sensor encounters an error, or when a daily or custom timed event occurs. This makes it easy to keep track of what is happening with your IoT device and react to any change or issue that may arise.

With Notify Mi, you can also `attach a file` with your text or email message. The maximum file size allowed is 1 MB and you can use any of the 69 supported file types, thus providing you flexibility in the type of attachment you want to include in your messages.

### Table of Contents
- [Purpose](#purpose)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Special Thanks](#special-thanks)

#### Purpose:

Sending notifications through your Gmail account is not a novel idea. Notify Mi is designed to be a `modular` and `reliable` way to send notifications without having to spend time and effort figuring out how to do it each time you want to add this feature to your project. Plus, the implementation process should be straightforward and `take only a couple minutes`. This way, you can focus on other aspects of your project and save time. 

#### Getting Started:

```python
# 1. generate an app password for your gmail account 
# see https://www.getmailbird.com/gmail-app-password/
# 2. install notify_mi using pip
pip install notify_mi

# ✔️ That's it, now you are ready to use
```

#### Usage:

###### Import
```python
from notify_mi import notify
```

###### Text messsage Only
```python
# send only a text message
# include phone_number and phone_provider
notify.send_message(message = "Hello World!", ("gmail", "password"), 
    phone_number = "your_number", phone_provider= "select from list below")
```

###### Text + Email
```python
# send text message + email
# include phone_number, phone_provider, and receiver email
notify.send_message("Hello World!", ("gmail", "password"), phone_number = "your_number", phone_provider= "select from list below", send_to = "name@email.com")
```

###### Email Only
```python
# send only email
# include receiver email
notify.send_message("Hello World!", send_to = "name@email.com")
```

###### Optional Paramters
```python
# add a subject line to the message
notify.send_message(subject = "EMERGENCY", message = "No sweets detected in fridge!")

# add a file attachment (69 file types supported)
notify.send_message(subject = "I found it", message = "My dream car", file_attachment = "/path/car.png")

# run without blocking main thread
notify.send_message("Hello World!", threaded = True)
```

##### List of Phone Providers
```python
# Select From: 
"AT&T", "Boost Mobile", "C-Spire", "Cricket Wireless", 
"Consumer Cellular", "Google Project Fi", "Metro PCS", 
"Mint Mobile", "Page Plus", "Republic Wireless", "Sprint",
"Straight Talk", "T-Mobile", "Ting", "Tracfone", 
"U.S. Cellular", "Verizon", "Virgin Mobile", and "Xfinity Mobile"
```

#### Special Thanks:
[Alfredo Sequeida](https://github.com/AlfredoSequeida) for writing a detailed [article](https://www.alfredosequeida.com/blog/how-to-send-text-messages-for-free-using-python-use-python-to-send-text-messages-via-email/) and for making a great [video](https://www.youtube.com/watch?v=4-ysecoraKo&t=2s) that went step by step on how to send text messages using python. It was very useful for one of my projects so I am adding to what he did so that other people can find it useful.  
