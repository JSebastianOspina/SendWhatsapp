# SendWhatsapp
Send whatsapp message throw python using Twilio api


To send a whatsapp mesagge throw Twilio api, you need to have all this item ready before you start.

  - Python 2.X or 3
  - Virtualenv package 
  - Twilio helper library
  - Pip 

# Setting up Python!

  If you are running an ubuntu 16.x or lower, you will have python 2 installed by default. Also, if you have update your python version, or installed Python3 before, you can use it.

# Virtualenv
If you are not using the newest version of Python (that means you are using Python 2) , you have to install Virtualenv package.

But first, we are going to Create a new folder for working on our proyect.
The new folder will be created /root/%user/%Desktop/%FolderforProyect

```sh
$ cd Desktop
$ mkdir WhatsappTextSender
$ cd WhatsappTextSender
```
For downloading the resources, you need to have **Pip installed**, if you doesn't, use the following code lines 
```sh
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python get-pip.py
```
At this point, we are able to install Virtualenv.
```sh
$sudo pip install virtualenv
```
Then, use the following code for creating a new virtual enviroment
```sh
$virtualenv pywhatsapp
```
If you have Python 3 installed, you only need to use the following code:
```sh
$python3 -m venv pywhatsapp
```
Finally, for both versions (2 or 3), use this command for getting inside our virtual enviroment.
```sh
$source ./pywhatsapp/bin/activate
```
Now, we have to download the Twilio's Python library
```sh
$pip install twilio
```
# Twilio Setup (Register and activation)
Register on the website twilio.com, confirm your email and cellphone number, then, go to the following link https://www.twilio.com/console/sms/whatsapp/learn

You will have to start the sandbox via Whatsapp, for this step, you have to send a message to the number that the website will provide you.

You can easily send the message using this url
http://wa.me/14155238886
Remplace "14155238886" for the number that the website provided you.
Then send the message  **join upon-memory**

Our account is done for using the api.
# Defining api credentials
On the top-rigth part of the website, you will find a button named "Show API Credentials". When you clic it, it will show your account sid and auth token.

In the terminal, use this instruction
```sh
$export TWILIO_ACCOUNT_SID='ACxxxxxxxx' # paste in Account SID between single quotes

$export TWILIO_AUTH_TOKEN='secret auth token' # paste Auth Token between single quotes
```
# Using the api!
Create a new Python file (Using Atom)
```sh
$Atom whatsapp.py
```
Then, paste this code
```sh
from twilio.rest import Client

# client credentials are read from TWILIO_ACCOUNT_SID and AUTH_TOKEN
client = Client()

b=raw_input("Ingrese el messaje: ") #Message you want to send
# this is the Twilio sandbox number that the website provide you
from_whatsapp_number='whatsapp:+14155238886'
# replace this number with your own WhatsApp Messaging number
to_whatsapp_number='whatsapp:+573213582239'

client.messages.create(body=b,
                       from_=from_whatsapp_number,
                       to=to_whatsapp_number)
```

For using it:
```sh
python whatsapp.py
```

The terminal will ask you for the message you want to send, when you give it, the script will automatically send the message to your cellpone.
 
