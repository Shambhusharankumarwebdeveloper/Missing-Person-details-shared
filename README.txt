MISSING PERSON ALERT - LOCAL SERVER
===================================
Why: opening the page from inside Claude/preview makes WhatsApp refuse to load.
Running it from this server opens it as a normal web page, so WhatsApp, Gmail
and the Mail app buttons work. It can also email every agency automatically.

1) Put server.py and index.html in the SAME folder.
2) Install Python 3 (python.org) if you do not have it. No other packages needed.
3) (Only for auto email) In your Google account turn on 2-Step Verification,
   then create an App Password: https://myaccount.google.com/apppasswords
4) Open a terminal / PowerShell in that folder and run:

   Windows PowerShell:
     $env:GMAIL_USER="yourname@gmail.com"
     $env:GMAIL_APP_PASSWORD="xxxx xxxx xxxx xxxx"
     python server.py

   Mac / Linux:
     export GMAIL_USER="yourname@gmail.com"
     export GMAIL_APP_PASSWORD="xxxx xxxx xxxx xxxx"
     python3 server.py

5) Open http://localhost:8000 in Chrome / Edge / Safari.
   Fill the 3 steps. In step 3:
   - "Email all agencies now" emails every agency that has an email, with photos.
   - WhatsApp / Gmail / Mail app buttons open normally (WhatsApp still needs you
     to press Send in each chat; WhatsApp does not allow automatic sending).

Notes
- The server only listens on your own computer (127.0.0.1). Keep it that way:
  it holds your Gmail App Password. Stop it with Ctrl+C when finished.
- To use it from your phone: run it on a computer, and use the phone only for
  WhatsApp from the downloaded page, or run Python on the phone (Termux).
- Fully automatic WhatsApp needs the WhatsApp Business Cloud API (Meta account,
  approved templates). Ask if you want that added.
