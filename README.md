# WhatsApp Selenium Client

[![Python Version](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/downloads/)
[![Selenium Version](https://img.shields.io/badge/Selenium-4.x.x-brightgreen.svg)](https://pypi.org/project/selenium/)

A easy-to-use Python class for automating interactions with WhatsApp Web using Selenium. This tool allows you to programmatically send and receive messages, open chats, and manage conversation flows directly from your Python scripts.

## 🚀 Features

- 📱 **Automated WhatsApp Web Login**: Seamlessly open WhatsApp Web and authenticate via QR code scanning.
- 💬 **Message Sending**: Send text messages to any chat.
- 📥 **Message Retrieval**: Fetch the latest incoming messages from your chats.
- 🔄 **Conversation Flow**: Facilitate interactive conversations with the `interact` method.
- 🔍 **Chat Navigation**: Open and navigate to specific chats by name or ID.

## 📚 API Reference

### `ClientWhatsAppSelenium`

#### `__init__(self, chat_name: str, slow_mode: bool = False)`

- **Description**: Initializes the WhatsApp client, opens WhatsApp Web, and navigates to the specified chat.
- **Parameters**:
  - `chat_name` (str): The name or ID of the WhatsApp chat to interact with.
  - `slow_mode` (bool, optional): If `True`, increases wait times to handle slower network connections. Default is `False`.

#### `wait(self, seconds: float)`

- **Description**: Pauses execution for the specified time, adjusted by `slow_mode` if enabled.
- **Parameters**:
  - `seconds` (float): Number of seconds to wait.

#### `open_chat(self, chat_name: str)`

- **Description**: Opens the chat with the specified name or ID.

#### `get_last_assistant_message(self) -> Optional[str]`

- **Description**: Retrieves the last incoming message from the current chat.

#### `is_user_last_message_sender(self) -> Optional[bool]`

- **Description**: Checks if the last message was sent by the user.

#### `send_message(self, text: str)`

- **Description**: Sends a text message to the current chat.
- **Parameters**:
  - `text` (str): The message content to send.

#### `interact(self, history: List[Dict[str, str]], messages: List[Dict[str, str]], retry_interval: int = 5) -> Dict[str, str]`

- **Description**: Sends messages and awaits a response, facilitating a conversational exchange.
- **Parameters**:
  - `history` (List[Dict[str, str]]): Conversation history.
  - `messages` (List[Dict[str, str]]): New messages to send.
  - `retry_interval` (int, optional): Time in seconds between checks for new messages. Default is `5`.

## ⚠️ Important Notes

- **First-Time Login**: Upon first execution, you'll need to scan the WhatsApp Web QR code. The session data is stored in `./chrome-data`, so subsequent runs won't require re-authentication.
- **Session Data**: Ensure that the `chrome-data` directory is secure, as it contains your session information.

## 🛡️ Disclaimer

This project is intended for educational and personal use only. Automating interactions with WhatsApp may violate their. Use this tool responsibly and at your own risk.

## 📝 License

This project is licensed under the Apache License.

---

_Thank you for using WhatsApp Selenium Client! If you find this project helpful, please give it a ⭐ on GitHub._