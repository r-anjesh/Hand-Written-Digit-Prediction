Python (Selenium) Assignment - Email Automation
Overview
This project is a Flask application designed to automate the process of sending emails with attachments using Python's smtplib library. It securely retrieves email credentials from environment variables and sends emails via Gmail's SMTP server.

Functionality
Email Sending:
Sends an email with attachments (confirmation_page.png, resume.pdf, documentation.pdf) to designated recipients.
Email Content:
Includes a subject line indicating the purpose of the email: "Python (Selenium) Assignment - [Your Name]".
Provides a brief message with links to related GitHub repositories.
Setup Instructions
Clone the Repository:

bash
Copy code
git clone https://github.com/r-anjesh/Python-Development.git
cd Python-Development/Assignment
Set Up Environment Variables:

Create a .env file in the root directory:
makefile
Copy code
SENDER_EMAIL=your_email@example.com
RECEIVER_EMAIL=tech@themedius.ai
EMAIL_PASS=your_email_password
CC_EMAIL=hr@themedius.ai
Install Dependencies:

Copy code
pip install Flask python-dotenv
Run the Application:

Copy code
python app.py
Access the Application:

Open your web browser and go to http://127.0.0.1:5000/.
Click on the link to send the email: http://127.0.0.1:5000/send-email.
Security Considerations
This application uses environment variables (SENDER_EMAIL, RECEIVER_EMAIL, EMAIL_PASS, CC_EMAIL) to securely manage sensitive information like email credentials.
File Structure
css
Copy code
Python-Development/
│
├── Assignment/
│   ├── app.py
│   ├── confirmation_page.png
│   ├── resume.pdf
│   ├── documentation.pdf
│   └── README.md
│
└── Day51/
    └── main.py
Additional Notes
Ensure that the attachments (confirmation_page.png, resume.pdf, documentation.pdf) are present in the same directory as the Flask application (app.py).
For any questions or issues, contact [Your Name] at your_email@example.com.
