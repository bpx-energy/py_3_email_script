# py_3_email_script
Send emails, including attachments using python.



Steps to send mail with Attachments from email account:

For adding an attachment, you need to import:
import smtplib
from email.mime.multipart import MIMEMultipart
from email.mime.text import MIMEText
from email.mime.base import MIMEBase
from email import encoders
These are some libraries which will make our work simple. These are the native libraries and you dont need to import any external library for this.

Firstly, create an instance of MIMEMultipart, namely “msg” to begin with.
Mention the sender’s email id, receiver’s email id and the subject in the “From”, “To” and “Subject” key of the created instance “msg”.
In a string, write the body of the message you want to send, namely body. Now, attach the body with the instance msg using attach function.
Open the file you wish to attach in the “rb” mode. Then create an instance of MIMEBase with two parameters. First one is ‘_maintype’ amd the other one is ‘_subtype’. This is the base class for all the MIME-specific sub-classes of Message.
Note that ‘_maintype’ is the Content-Type major type (e.g. text or image), and ‘_subtype’ is the Content-Type minor type (e.g. plain or gif or other media).
set_payload is used to change the payload the encoded form. Encode it in encode_base64. And finally attach the file with the MIMEMultipart created instance msg.
After finishing up these steps, follow the instructions described in the previous article to create a session, secure it and check the authenticity and then after sending the mail, terminate the session.
