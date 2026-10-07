# sending_emailautomatically

Automatically sends an e-mail with the two most recent files from the Downloads folder attached. Built for a monthly routine: send the invoice files to a billing team.

## How it works

The notebook has two steps.

1. **Find the files.** Lists the Downloads folder, sorts by modification time and takes the two latest files.
2. **Send the e-mail.** Uses `pyautogui` to drive the browser:
   - opens a new Chrome tab and goes to the web mail (already logged in);
   - presses `n` to start a new message, fills in the recipient, a subject with the current month name and the message body;
   - clicks the attach button twice to add both files;
   - sends with Ctrl + Enter.

The message is in Portuguese. The month name comes from the `pt_BR` locale and the text goes through the clipboard (`pyperclip`) so that accents and punctuation are kept. `time.sleep` calls leave time for pages and dialogs to load.

## Requirements

- Python 3 with `pyautogui` and `pyperclip`.
- Windows with Chrome and a web mail account already logged in.
- The `pt_BR` locale available on your system.

## How to run

1. Change the Downloads path, the recipient address (a placeholder is used here) and the message text.
2. Use `pyautogui.position()` to find the screen coordinates of the attach button on your screen and update them.
3. Close other browser tabs and run the cells.

## Notes

- Clicks use fixed screen coordinates and fixed waits, so it only works on the screen setup it was recorded on until you adjust it.
- A practice project for desktop automation with `pyautogui`. The recipient and the company in the message are placeholders.
