TAN NGUYEN
EE104
Lab 8

YouTube link: https://www.youtube.com/watch?v=eHglsYHbIDw
Github link: https://github.com/leehuy21/Lab-8

Introduction: This readme.txt file will provide you with all the information you need to run my programs on your local machine.

Requirement
Before running the programs, you will need to ensure that your computer meets the following requirements:
Python 3.6 or later is installed on your machine.
The required Python packages are installed. The required packages for each program are listed below.

1. Client server solution
a. Description

This program will enable you to create a local host, allowing you to upload up to 75 text files or Word documents. Once uploaded, the program will extract relevant information from these files and use it to answer questions. Whether you're looking to quickly search for specific information or get a deeper understanding of the content, this program will provide you with the tools to easily access and utilize the information contained within your files.
This version aims to provide more clarity and emphasis on the benefits of using the program.

b. Running the program
#Step 1:Set up OpenAI API and Pinecone API keys and index name. Retrieve from these sites:
https://platform.openai.com/docs/api-reference/introduction 
https://www.pinecone.io/

For Index, select "FROM COLLECTION" and pick NEW
index_name="ee104"
Dimensions=1536, Metric=Cosine, Pod Type= S1
then click the button "CREATE INDEX"

#Step 2:Run the Google Colab from the first Jupiter cell to the second-last one.
You will see a pop-up window with the title "Creating index openai-trec"
click on "OPEN COLAB" in another tab or another window.
It will look like this: https://colab.research.google.com/github/pinecone-io/examples/blob/master/integrations/openai/semantic_search_openai.ipynb 

#Step 3: Download the source code from https://github.com/openai/openai-cookbook.

You will need Node,js and nam for the Next.js client.
Run this command:
pip install openai
npm install openai

DOWNLOAD THE SOURCE CODE
# Go to: https://github.com/openai/openai-cookbook

# Create a ".env" file using NotePad++ or any text editor that allow you to save 
#  in this format .env
#  and type this line below, then save the file as "all type" with file name ".env"
#  env stands for environment
# OPEN_API_KEY = "YOUR_API_KEY"
# YOUR OPENAI ORG KEY = "YOUR_OPENAI_ORG_KEY"
# PINECONE_API_KEY="YOUR_PINECONE_API_KEY"
# PINECONE_ENVIRONMENT="Your_environment"

For step 4 and 5 you can run in two separate Power Shell to save time, one for Server, and one for Client

#Step 4: Run in Server directory
1. Change directory to your Server directory.
2. Fill out the config.yaml file with your Pinecone API key, index name and environment.
3. In your PowerShell window, run this command:
pip install openai
npm install openai

Then run following commands one by one 
python install virtualenv
python -m venv venv
.\venv\Scripts\activate

pip install -r .\requirements.txt 


Finally run, python app.py
# You should now see the followings:
 * Serving Flask app 'app'
 * Debug mode: on
INFO:werkzeug:←[31m←[1mWARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.←[0m
 * Running on http://127.0.0.1:8080
INFO:werkzeug:←[33mPress CTRL+C to quit←[0m
INFO:werkzeug: * Restarting with stat
WARNING:werkzeug: * Debugger is active!
INFO:werkzeug: * Debugger PIN: 576-986-598

#Step 5: Run on Client directory
1. In Powershell, change directory to Client
pip install openai
npm install openai

2. Type the command to run the Next.js client:
Npm run dev 
You should see something similar to the followings:
    > file-q-and-a@0.1.0 dev
    > next dev

    ready - started server on 0.0.0.0:3000, url: http://localhost:3000
    event - compiled client and server successfully in 2.7s (166 modules)
    wait  - compiling...
    event - compiled successfully in 124 ms (133 modules)
    Attention: Next.js now collects completely anonymous telemetry regarding usage.
    This information is used to shape Next.js' roadmap and prioritize features.
    You can learn more, including how to opt-out if you'd not like to participate in this anonymous program, by visiting the following URL:
    https://nextjs.org/telemetry

    wait  - compiling / (client and server)...
    event - compiled client and server successfully in 1962 ms (757 modules)

#Step 6: Open http://localhost:3000 with your browser to see the app.
Upload your Q and A file to the site
Search for a content within that file.



2. Web Crawl Q&A
Description:
This program is designed to assist you in building a Question and Answer tool about San Jose State University. It will retrieve data from the SJSU.edu website, and provide answers to any inquiries related to the site.

Running the program
#Step1: Similar to the previous part, create a API key on this website
https://platform.openai.com/docs/api-reference/introduction 
Go to this site to get API key, https://platform.openai.com/account/api-keys 

Run this command on Powershell, pip install openai
# Create a folder. For this project, let's call it C:\web-crawl-q-and-a 
#  using the Linux command "md" (make directory)
PS C:\>md web-crawl-q-and-a 

# Use the "cd" (change directory) to go inside the directory:
PS C:\> cd .\web-crawl-q-and-a\
PS C:\web-crawl-q-and-a>

# Create a ".env" file using NotePad++ or any text editor that allow you to save 
#  in this format .env
#  and type this line below, then save the file as "all type" with file name ".env"
#  env stands for environment
OPEN_API_KEY = "YOUR_API_KEY"

#Step2: DOWNLOAD THE CODE:
Clone the full code for this tutorial on GitHub and put it in a local directory 
on the computer. For example: put the files in C:\web-crawl-q-and-a 
https://github.com/openai/openai-cookbook/tree/main/apps/web-crawl-q-and-a

#Step 3: PREPARE THE ENVIRONMENT:


PS C:\> cd .\web-crawl-q-and-a\

PS C:\web-crawl-q-and-a> python install virtualenv  (or c:\python310\Python install virtualenv if you have to use the absolute path)
PS C:\web-crawl-q-and-a> python -m venv env
PS C:\web-crawl-q-and-a> ls
    Directory: C:\web-crawl-q-and-a
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----          3/3/2023   8:28 AM                env
-a----          3/2/2023   5:56 PM           1342 requirements.txt
-a----          3/2/2023   5:56 PM          81844 web-qa.ipynb
-a----          3/2/2023   5:56 PM          13302 web-qa.py

#Notice that the new directory "env" has been created.

PS C:\web-crawl-q-and-a> ls env
    Directory: C:\web-crawl-q-and-a\venv
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----          3/3/2023   8:26 AM                Include
d-----          3/3/2023   8:26 AM                Lib
d-----          3/3/2023   8:26 AM                Scripts
-a----          3/3/2023   8:26 AM             77 pyvenv.cfg


PS C:\web-crawl-q-and-a> .\env\Scripts\activate
(env) PS C:\web-crawl-q-and-a>

Go to powershell window and run,
PS C:\OpenAI\web-crawl-q-and-a> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine       Undefined

PS C:\OpenAI\web-crawl-q-and-a> Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope CurrentUser

Execution Policy Change
The execution policy helps protect you from scripts that you do not trust. Changing the execution policy might expose
you to the security risks described in the about_Execution_Policies help topic at
https:/go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): Y
PS C:\OpenAI\web-crawl-q-and-a> Get-ExecutionPolicy -List
 Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    Unrestricted
 LocalMachine    Unrestricted


PS C:\OpenAI\web-crawl-q-and-a> .\env\Scripts\activate

#### You can learn more about Powershell policy here:
####   https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.3#use-group-policy-to-manage-execution-policy

#The command below will take some time to finish all installations
(env) PS C:\web-crawl-q-and-a> pip install -r requirements.txt
Collecting aiohttp==3.8.3
  Using cached aiohttp-3.8.3-cp310-cp310-win_amd64.whl (319 kB)
  ....
 Successfully installed Pillow-9.4.0 PyYAML-6.0 Pygments-2.14.0 aiohttp-3.8.3 aiosignal-1.3.1 appnope-0.1.3 asttokens-2.2.1 async-timeout-4.0.2 attrs-22.2.0 backcall-0.2.0 beautifulsoup4-4.11.1 blobfile-2.0.1 bs4-0.0.1 certifi-2022.12.7 charset-normalizer-2.1.1 colorama-0.4.6 comm-0.1.2 contourpy-1.0.7 cycler-0.11.0 debugpy-1.6.5 decorator-5.1.1 docopt-0.6.2 entrypoints-0.4 executing-1.2.0 filelock-3.9.0 fonttools-4.38.0 frozenlist-1.3.3 html-1.13 huggingface-hub-0.11.1 idna-3.4 ipykernel-6.20.1 ipython-8.8.0 jedi-0.18.2 joblib-1.2.0 jupyter_client-7.4.8 jupyter_core-5.1.3 kiwisolver-1.4.4 lxml-4.9.2 matplotlib-3.6.3 matplotlib-inline-0.1.6 multidict-6.0.4 nest-asyncio-1.5.6 numpy-1.24.1 openai-0.26.1 packaging-23.0 pandas-1.5.2 parso-0.8.3 pexpect-4.8.0 pickleshare-0.7.5 pipreqs-0.4.11 platformdirs-2.6.2 plotly-5.12.0 prompt-toolkit-3.0.36 psutil-5.9.4 ptyprocess-0.7.0 pure-eval-0.2.2 pycryptodomex-3.17 pyparsing-3.0.9 python-dateutil-2.8.2 pytz-2022.7.1 pywin32-305 pyzmq-24.0.1 regex-2022.10.31 requests-2.28.1 scikit-learn-1.2.0 scipy-1.10.0 six-1.16.0 soupsieve-2.3.2.post1 stack-data-0.6.2 tenacity-8.1.0 threadpoolctl-3.1.0 tiktoken-0.1.2 tokenizers-0.13.2 tornado-6.2 tqdm-4.64.1 traitlets-5.8.1 transformers-4.25.1 typing_extensions-4.4.0 urllib3-1.26.13 wcwidth-0.2.5 yarg-0.1.9 yarl-1.8.2
 
#You may see the following warning. You can just run the command to upgrade PIP as you wish:
WARNING: You are using pip version 22.0.4; however, version 23.0.1 is available.
You should consider upgrading via the 'C:\web-crawl-q-and-a\env\Scripts\python.exe -m pip install --upgrade pip' command.
(env) PS C:\web-crawl-q-and-a> C:\web-crawl-q-and-a\env\Scripts\python.exe -m pip install --upgrade pip

pip


==================================================
LEARN ABOUT OpenAI API
https://platform.openai.com/docs/tutorials/web-qa-embeddings


==================================================
BUILD THE WEB CRAWLER & CUSTOMIZE WITH YOUR OWN URL
https://platform.openai.com/docs/tutorials/web-qa-embeddings/setting-up-a-web-crawler

You will want to use your own URL so replace the root URL in the file web-qa.py 
with your own URL:

(env) PS C:\web-crawl-q-and-a> ls
    Directory: C:\web-crawl-q-and-a
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----          3/3/2023   8:33 AM                env
-a----          3/2/2023   5:56 PM           1342 requirements.txt
-a----          3/2/2023   5:56 PM          81844 web-qa.ipynb
-a----          3/2/2023   5:56 PM          13302 web-qa.py

# Open to edit the file web-qa.py and add this line at the top right under library import section.
# Double check not to add the same lines if the code is already existing:
import os
import openai #remember to pip install pandas openai
from dotenv import load_dotenv  #remember to pip install python-dotenv
load_dotenv()

#Sign up for OpenAI here https://beta.openai.com/signup
# and obtain an API key from here https://platform.openai.com/account/api-keys
openai.api_key = os.getenv("OPENAI_API_KEY")


# Replace the following 2 lines of code. Save the file. 

# Define root domain to crawl
domain = "openai.com"
full_url = "https://openai.com/"

==> change it to 
# Define root domain to crawl
domain = "www.sjsu.edu"
full_url = "https://www.sjsu.edu/"


# Here is the top of the file web-qa.py with all needed imports
################################################################################
### Step 1
################################################################################

import requests
import re
import urllib.request
from bs4 import BeautifulSoup
from collections import deque
from html.parser import HTMLParser
from urllib.parse import urlparse
import os
import pandas as pd
import tiktoken #remember to pip install tiktoken
import openai
from openai.embeddings_utils import distances_from_embeddings
import numpy as np
from openai.embeddings_utils import distances_from_embeddings, cosine_similarity

from dotenv import load_dotenv  #remember to pip install python-dotenv
load_dotenv()

openai.api_key = os.getenv("OPENAI_API_KEY")


==================================================
MODIFY FUNCTION SO THE PROGRAM WILL NOT STOP IF A FILE DOES NOT EXIST

# Make change to this function in Step 4
def crawl(url):
    # Parse the URL and get the domain
    local_domain = urlparse(url).netloc

    # Create a queue to store the URLs to crawl
    queue = deque([url])

    # Create a set to store the URLs that have already been seen (no duplicates)
    seen = set([url])

    # Create a directory to store the text files
    if not os.path.exists("text/"):
            os.mkdir("text/")

    if not os.path.exists("text/"+local_domain+"/"):
            os.mkdir("text/" + local_domain + "/")

    # Create a directory to store the csv files
    if not os.path.exists("processed"):
            os.mkdir("processed")

    # While the queue is not empty, continue crawling
    while queue:

        # Get the next URL from the queue
        url = queue.pop()
        print(url) # for debugging and to see the progress

        try:
            # Save text from the url to a <url>.txt file
            with open('text/'+local_domain+'/'+url[8:].replace("/", "_") + ".txt", "w", encoding="UTF-8") as f:

                # Get the text from the URL using BeautifulSoup
                soup = BeautifulSoup(requests.get(url).text, "html.parser")

                # Get the text but remove the tags
                text = soup.get_text()

                # If the crawler gets to a page that requires JavaScript, it will stop the crawl
                if ("You need to enable JavaScript to run this app." in text):
                    print("Unable to parse page " + url + " due to JavaScript being required")

                # Otherwise, write the text to the file in the text directory
                f.write(text)
        except:
            #do nothing

            # Get the hyperlinks from the URL and add them to the queue
            for link in get_domain_hyperlinks(local_domain, url):
                if link not in seen:
                    queue.append(link)
                    seen.add(link)




==================================================
BUILDING AN EMBEDDING INDEX USING CSV FILE
https://platform.openai.com/docs/tutorials/web-qa-embeddings/building-an-embeddings-index 

# Note that the codes are in the same file web-qa.py but you should read to understand 
# each code segment.

# Now edit file web-qa.py and change the following section in STEP 13 of the file:
#  STEP 13 of file web-qa.py 
print(answer_question(df, question="Where is SJSU?", debug=False))

print(answer_question(df, question="Information about the Welcome Center?"))

print(answer_question(df, question="What is EE104?"))

while (True):
    prompt = input("\nEnter your question: \n")
    print(answer_question(df, question=prompt))


==================================================
IMPROVE YOUR PRODUCTIVITY BY USING VECTOR DATABASE SOLUTION
https://platform.openai.com/docs/guides/embeddings/how-can-i-retrieve-k-nearest-embedding-vectors-quickly

# Optional: if you want to learn how to improve the performance and productitity, use this method

==================================================
RUN THE CODE FOR THE FIRST TIME & CRAWL THE WEBSITE TO BUILD THE CSV FILE
# Note: subsequently you will not need to craw the website again unless it is updated. See next step.

(env) PS C:\web-crawl-q-and-a> pip install tiktoken
(env) PS C:\web-crawl-q-and-a> pip install pandas openai
(env) PS C:\web-crawl-q-and-a> pip install python-dotenv
(env) PS C:\web-crawl-q-and-a> pip install bs4
(env) PS C:\web-crawl-q-and-a> pip install matplotlib 
(env) PS C:\web-crawl-q-and-a> pip install plotly 
(env) PS C:\web-crawl-q-and-a> pip install scipy
(env) PS C:\web-crawl-q-and-a> pip install sklearn -use-pep517
(env) PS C:\web-crawl-q-and-a> pip install -U scikit-learn scipy matplotlib

Collecting python-dotenv
  Downloading python_dotenv-1.0.0-py3-none-any.whl (19 kB)
Installing collected packages: python-dotenv
Successfully installed python-dotenv-1.0.0


#Note: you can also execute the file web-qa.py within Anaconda.
# just make sure you execute all the pip install * commands above.
################################
(env) PS C:\web-crawl-q-and-a> python web-qa.py
################################
This will take some time to crawl the website and build your CSV file.
After that, you can start querying the information from the website.


# Check in your C:\web-crawl-q-and-a\text directory and you will see a new directories
#  created:  
C:\web-crawl-q-and-a\text\www.sjsu.edu

# Also note that you will see this directory:
C:\OpenAI\web-crawl-q-and-a\processed

#### DEBUG NOTES ##################################
####
# If you see the following errors, 
openai.error.RateLimitError: Rate limit reached for default-global-with-image-limits in organization org-OcV0YS9QWhowhAVXIcyVW9OZ on requests per min. Limit: 60 / min. Please try again in 1s. Contact support@openai.com if you continue to have issues. Please add a payment method to your account to increase your rate limit. Visit https://platform.openai.com/account/billing to add a payment method.

# Then simply remove some files from the directory  
#   C:\OpenAI\web-crawl-q-and-a\text\www.sjsu.edu
#   until you no longer see that error message
#  I simply moved all files related to career, internships, and AS to a backup folder
#   outside of that directory C:\OpenAI\web-crawl-q-and-a\text\www.sjsu.edu
#  It will work when you have about 5-10 files in the directory.
# Also change MAX_TOKEN to lower value will help.
####
#### END OF DEBUG ##################################

# If you want to stop, type CTL-C then type "exit" to stop the program in Powershell

==================================================
SUBSEQUENT WEB SCRAPPING:

# Modify file web-qa.py and comment out this code at then end of Step 5 in the code
#crawl(full_url)

# Note: if you need to crawl the web again, just uncomment this line and 
#  run the code again.

==================================================

#### These are a few websites being scrapped from www.sjsu.edu:
ww.sjsu.edu_careers
ww.sjsu.edu_giving
ww.sjsu.edu_healthadvisories
ww.sjsu.edu_it_support_service-desk_index.php
ww.sjsu.edu_medical
ww.sjsu.edu_winter_contact_sign-up_index.html
www.sjsu.edu

----
File ww.sjsu.edu_careers has the following key points in this format:
Header
   Text
   
Work at an SJSU Auxiliary
In addition to the state jobs on campus, SJSU has five auxiliary organizations that
recruit regularly for student, staff and faculty positions.

Hire SJSU Talent
Learn how to sustain or expand your organization's workforce through the business-to-business services offered by the SJSU Career Center.       

Doing Business with SJSU
Interested in submitting a bid for products or services? SJSU Contracts and Purchasing
Services is responsible for selecting the best source of goods and services for the
university in compliance with a wide variety of accessibility, ethics, fair practices
and other policies.  

----
File ww.sjsu.edu_medical has following key points:

Stay Healthy, Spartans!
ALL students are expected to provide proof of COVID-19 vaccine status or indicate
a qualifying exemption. Visit our website for more information.

Online Services (Patient Portal)
Call 408-924-6122 to make an appointment. The Student Health Center uses a secure
and confidential online system which allows currently enrolled students to view appointments
and their electronic health information, message a provider and more.
                  
Get Your Shots
Get caught up on all required immunizations before you start at SJSU. Flu shots are
also available.   

Payments and Fees
Health insurance is not required to visit the Student Wellness Center if you are enrolled
as a student at SJSU. The Mandatory Health Fee (included with your tuition payment)
includes unlimited primary care visits at no additional charge. Some additional services may require a nominal fee, which can be paid online.

#### OPEN AI in action ##################################
####

########################
Here is the example of the output from the knowledge retained from this website:
https://www.sjsu.edu

(env) PS C:\web-crawl-q-and-a> python web-qa.py

Where is SJSU?

San José State University is located in San José, California.

tell me about work at an SJSU auxiliary?

Work at an SJSU auxiliary includes student, staff and faculty positions. In addition, SJSU has five auxiliary organizations that recruit regularly for these positions.

tell me about vaccine booster

SJSU has updated its vaccination policy to require boosters for the 2022 Spring semester. For more information on the CSU vaccination policy and how to verify your vaccination status, visit the Vaccination page.

Enter your question:
How to work at SJSU auxiliary and stay healthy?
To work at SJSU auxiliary and stay healthy, visit the Health Advisories website for the latest vaccination and mask information and to Report a Case.

Enter your question:
What is SJSU auxiliary
SJSU auxiliary refers to the five organizations on campus that recruit regularly for student, staff and faculty positions.

Enter your question:
how can business work with sjsu
Interested in submitting a bid for products or services? SJSU Contracts and Purchasing Services is responsible for selecting the best source of goods and services for the university in compliance with a wide variety of accessibility, ethics, fair practices and other policies.

Enter your question:
how can business ensure employees get the flu shots?
Businesses can ensure employees get flu shots by providing access to flu shots at the workplace or by providing information about nearby locations where flu shots are available.

Enter your question:
how can business pay for health insurance for their employees at SJSU?
I don't know.

Enter your question:
How can sjsu employee pay for health insurance?
I don't know.

Enter your question:
do I need health insurance to visit the student wellness center?
No, health insurance is not required to visit the Student Wellness Center if you are enrolled as a student at SJSU.

Enter your question:
What is the patient portal phone number
(408) 924-1530

Enter your question:
# If you want to stop, type CTL-C then type "exit" to stop the program in Powershell
Enter your question:
exit
Traceback (most recent call last):
  File "C:\web-crawl-q-and-a\web-qa.py", line 437, in <module>
    prompt = input("\nEnter your question: \n")
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
KeyboardInterrupt

#### End of OPEN AI in action ##################################

3. Traffic Controller, Part 2
The next step in building a Simple Traffic Controller involves creating a software-based Finite State Machine to replace the hardware-based one used in Part 1. The controller's primary function is to ensure that East Santa Clara Street has a green signal and that pedestrian walkways are available, except in cases where a pedestrian crossing request from 7th Street or a vehicle entering from 7th Street is detected.

To complete the hardware component, you will require specific materials, including LED traffic signals, a 7-segment display for the pedestrian countdown signal at 7th Street, a push-button for pedestrian input, a BCD-to-7-segment decoder 74LS47, a clock, a binary up/down counter with clear 74LS193, a decade counter 74LS90, resistors, capacitors, and other open-collector signal connections. You will need to use your own breadboard from your previous courses.

By following the state machine's logic, you can implement a circuit with a 7-segment display, counter, and LEDs that mimics the functionality of the traffic light controller.

##That’s it. Enjoy my programs
