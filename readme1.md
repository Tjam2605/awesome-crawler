#Webscraper Overview

Documentation for Project Overview, Instructions Inline Comments/Code 


o	The first construction of code is a very detailed prompt to chatGPT, that entails a request to generate a python based scraper sample.
The Prompt: “Create the code for a python-based web scraper that can collect different types of data from a website by extracting its html code”
The Python-Scraper Output With No Refinement:
import requests
from bs4 import BeautifulSoup

def web_scraper(url):
    # Send a GET request to the website
    response = requests.get(url)
    
    # Check if the request was successful
    if response.status_code == 200:
        # Parse the HTML content using Beautiful Soup
        soup = BeautifulSoup(response.text, 'html.parser')
        
        # Extract headlines (e.g., all <h2> tags)
        headlines = [headline.get_text() for headline in soup.find_all('h2')]
        
        # Extract all links (e.g., <a> tags with href attributes)
        links = [a['href'] for a in soup.find_all('a', href=True)]
        
        # Extract images (e.g., <img> tags with src attributes)
        images = [img['src'] for img in soup.find_all('img', src=True)]
        
        # Print extracted data
        print("Headlines:")
        for headline in headlines:
            print(f"- {headline}")
        
        print("\nLinks:")
        for link in links:
            print(f"- {link}")
        
        print("\nImages:")
        for image in images:
            print(f"- {image}")
    else:
        print(f"Failed to retrieve the page. Status code: {response.status_code}")

# Example usage:
web_scraper('https://example.com')  # Replace with the target website URL

o	Code Explanation **Refine this explanation in more detail**

1. **Sending a Request:** It sends a GET request to the specified URL using the `requests` library.
2. **Parsing HTML:** If the request is successful, it parses the HTML content of the page using Beautiful Soup.
3. **Extracting Data:**
   - **Headlines:** It extracts all `<h2>` tags, assuming these represent headlines. This can be adjusted to any tag or class relevant to the data needed.
   - **Links:** It collects all `<a>` tags with the `href` attribute, extracting URLs from the page.
   - **Images:** It retrieves all `<img>` tags with the `src` attribute to collect image URLs.
4. **Displaying Data:** The extracted data is printed to the console.

You can modify the tags and attributes in the `find_all` method calls to suit the structure of the target website. This script provides a basic framework for a web scraper that can be expanded and customized further for more complex data extraction tasks.

o	Results From Running The Code In Python
Using google colabortory for the python environment, some websites did not work but a few did, so that problem will be eradicated later on so it could be compatible with many websites. What was extracted are headlines, images & Links
Output from successful code request to random website https://pypi.org/project/beautifulsoup4/ 
:-
Headlines:
- Project description
- Project details
- 
Release history

Release notifications |
              RSS feed 


- Download files
- Help
- About PyPI
- Contributing to PyPI
- Using PyPI

Links:
- #content
- /
- /help/
- /sponsors/
- /account/login/
- /account/register/
- /help/
- /sponsors/
- /account/login/
- /account/register/
- /project/beautifulsoup4/
- #description
- #history
- #files
- https://docs.pypi.org/project_metadata/#verified-details
- /user/leonard/
- https://www.crummy.com/software/BeautifulSoup/bs4/download/
- https://www.crummy.com/software/BeautifulSoup/bs4/
- leonardr@segfault.org
- /search/?c=Development+Status+%3A%3A+5+-+Production%2FStable
- /search/?c=Intended+Audience+%3A%3A+Developers
- /search/?c=License+%3A%3A+OSI+Approved+%3A%3A+MIT+License
- /search/?c=Programming+Language+%3A%3A+Python
- /search/?c=Programming+Language+%3A%3A+Python+%3A%3A+3
- /search/?c=Topic+%3A%3A+Software+Development+%3A%3A+Libraries+%3A%3A+Python+Modules
- /search/?c=Topic+%3A%3A+Text+Processing+%3A%3A+Markup+%3A%3A+HTML
- /search/?c=Topic+%3A%3A+Text+Processing+%3A%3A+Markup+%3A%3A+SGML
- /search/?c=Topic+%3A%3A+Text+Processing+%3A%3A+Markup+%3A%3A+XML
- #description
- #data
- #history
- #files
- https://www.crummy.com/software/BeautifulSoup/bs4/doc/
- https://www.crummy.com/software/BeautifulSoup/bs4/
- https://www.crummy.com/software/BeautifulSoup/bs4/doc/
- https://groups.google.com/group/beautifulsoup/
- https://code.launchpad.net/beautifulsoup/
- https://bugs.launchpad.net/beautifulsoup/
- https://bazaar.launchpad.net/~leonardr/beautifulsoup/bs4/view/head:/CHANGELOG
- https://tidelift.com/subscription/pkg/pypi-beautifulsoup4?utm_source=pypi-beautifulsoup4&utm_medium=referral&utm_campaign=readme
- https://www.crummy.com/software/BeautifulSoup/zine/
- https://docs.pypi.org/project_metadata/#verified-details
- /user/leonard/
- https://www.crummy.com/software/BeautifulSoup/bs4/download/
- https://www.crummy.com/software/BeautifulSoup/bs4/
- leonardr@segfault.org
- /search/?c=Development+Status+%3A%3A+5+-+Production%2FStable
- /search/?c=Intended+Audience+%3A%3A+Developers
- /search/?c=License+%3A%3A+OSI+Approved+%3A%3A+MIT+License
- /search/?c=Programming+Language+%3A%3A+Python
- /search/?c=Programming+Language+%3A%3A+Python+%3A%3A+3
- /search/?c=Topic+%3A%3A+Software+Development+%3A%3A+Libraries+%3A%3A+Python+Modules
- /search/?c=Topic+%3A%3A+Text+Processing+%3A%3A+Markup+%3A%3A+HTML
- /search/?c=Topic+%3A%3A+Text+Processing+%3A%3A+Markup+%3A%3A+SGML
- /search/?c=Topic+%3A%3A+Text+Processing+%3A%3A+Markup+%3A%3A+XML
- /help/#project-release-notifications
- /rss/project/beautifulsoup4/releases.xml
- /project/beautifulsoup4/4.13.0b2/
- /project/beautifulsoup4/4.12.3/
- /project/beautifulsoup4/4.12.2/
- /project/beautifulsoup4/4.12.1/
- /project/beautifulsoup4/4.12.0/
- /project/beautifulsoup4/4.11.2/
- /project/beautifulsoup4/4.11.1/
- /project/beautifulsoup4/4.11.0/
- /project/beautifulsoup4/4.10.0/
- /project/beautifulsoup4/4.9.3/
- /project/beautifulsoup4/4.9.2/
- /project/beautifulsoup4/4.9.1/
- /project/beautifulsoup4/4.9.0/
- /project/beautifulsoup4/4.8.2/
- /project/beautifulsoup4/4.8.1/
- /project/beautifulsoup4/4.8.0/
- /project/beautifulsoup4/4.7.1/
- /project/beautifulsoup4/4.7.0/
- /project/beautifulsoup4/4.6.3/
- /project/beautifulsoup4/4.6.2/
- /project/beautifulsoup4/4.6.1/
- /project/beautifulsoup4/4.6.0/
- /project/beautifulsoup4/4.5.3/
- /project/beautifulsoup4/4.5.2/
- /project/beautifulsoup4/4.5.1/
- /project/beautifulsoup4/4.5.0/
- /project/beautifulsoup4/4.4.1/
- /project/beautifulsoup4/4.4.0/
- /project/beautifulsoup4/4.3.2/
- /project/beautifulsoup4/4.3.1/
- /project/beautifulsoup4/4.3.0/
- /project/beautifulsoup4/4.2.1/
- /project/beautifulsoup4/4.2.0/
- /project/beautifulsoup4/4.1.3/
- /project/beautifulsoup4/4.1.2/
- /project/beautifulsoup4/4.1.1/
- /project/beautifulsoup4/4.1.0/
- /project/beautifulsoup4/4.0.5/
- /project/beautifulsoup4/4.0.4/
- /project/beautifulsoup4/4.0.3/
- /project/beautifulsoup4/4.0.2/
- /project/beautifulsoup4/4.0.1/
- https://packaging.python.org/tutorials/installing-packages/
- https://files.pythonhosted.org/packages/b3/ca/824b1195773ce6166d388573fc106ce56d4a805bd7427b624e063596ec58/beautifulsoup4-4.12.3.tar.gz
- #copy-hash-modal-737e7c28-44f5-4ec4-81e7-eb320661f91a
- https://files.pythonhosted.org/packages/b1/fe/e8c672695b37eecc5cbf43e1d0638d88d66ba3a44c4d321c796f4e59167f/beautifulsoup4-4.12.3-py3-none-any.whl
- #copy-hash-modal-f89baac4-5582-4cca-9ed1-67686397e17a
- #modal-close
- https://pip.pypa.io/en/stable/topics/secure-installs/#hash-checking-mode
- #modal-close
- #modal-close
- https://pip.pypa.io/en/stable/topics/secure-installs/#hash-checking-mode
- #modal-close
- https://packaging.python.org/tutorials/installing-packages/
- https://packaging.python.org/tutorials/packaging-projects/
- https://packaging.python.org/
- https://www.python.org/dev/peps/pep-0541/
- /help/
- https://blog.pypi.org
- https://dtdg.co/pypi
- /stats/
- /trademarks/
- /sponsors/
- /help/#feedback
- https://github.com/pypi/warehouse
- https://hosted.weblate.org/projects/pypa/warehouse/
- /sponsors/
- https://github.com/pypi/warehouse/graphs/contributors
- https://policies.python.org/python.org/code-of-conduct/
- /security/
- https://www.python.org/privacy/
- https://policies.python.org/pypi.org/Terms-of-Use/
- https://policies.python.org/pypi.org/Acceptable-Use-Policy/
- https://status.python.org/
- https://donate.pypi.org
- /trademarks/
- https://www.python.org/psf-landing
- https://www.python.org/psf-landing/
- /sitemap/
- https://aws.amazon.com/
- https://www.datadoghq.com/
- https://www.fastly.com/
- https://careers.google.com/
- https://www.python.org/psf/sponsors/#microsoft
- https://www.pingdom.com/
- https://getsentry.com/for/python
- https://statuspage.io

Images:
- /static/images/logo-small.8998e9d1.svg
- https://pypi-camo.freetls.fastly.net/c5caa34d0062a04d6d09cab71355954f188822a3/68747470733a2f2f7365637572652e67726176617461722e636f6d2f6176617461722f62383361616135653563383132393938376338633534663239373465383464333f73697a653d3530
- https://pypi-camo.freetls.fastly.net/c5caa34d0062a04d6d09cab71355954f188822a3/68747470733a2f2f7365637572652e67726176617461722e636f6d2f6176617461722f62383361616135653563383132393938376338633534663239373465383464333f73697a653d3530
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/blue-cube.572a5bfb.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- https://pypi.org/static/images/white-cube.2351a86c.svg
- /static/images/white-cube.2351a86c.svg
- https://pypi-camo.freetls.fastly.net/ed7074cadad1a06f56bc520ad9bd3e00d0704c5b/68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f707970692d6173736574732f73706f6e736f726c6f676f732f6177732d77686974652d6c6f676f2d7443615473387a432e706e67
- https://pypi-camo.freetls.fastly.net/8855f7c063a3bdb5b0ce8d91bfc50cf851cc5c51/68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f707970692d6173736574732f73706f6e736f726c6f676f732f64617461646f672d77686974652d6c6f676f2d6668644c4e666c6f2e706e67
- https://pypi-camo.freetls.fastly.net/df6fe8829cbff2d7f668d98571df1fd011f36192/68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f707970692d6173736574732f73706f6e736f726c6f676f732f666173746c792d77686974652d6c6f676f2d65684d3077735f6f2e706e67
- https://pypi-camo.freetls.fastly.net/420cc8cf360bac879e24c923b2f50ba7d1314fb0/68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f707970692d6173736574732f73706f6e736f726c6f676f732f676f6f676c652d77686974652d6c6f676f2d616734424e3774332e706e67
- https://pypi-camo.freetls.fastly.net/524d1ce72f7772294ca4c1fe05d21dec8fa3f8ea/68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f707970692d6173736574732f73706f6e736f726c6f676f732f6d6963726f736f66742d77686974652d6c6f676f2d5a443172685444462e706e67
- https://pypi-camo.freetls.fastly.net/d01053c02f3a626b73ffcb06b96367fdbbf9e230/68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f707970692d6173736574732f73706f6e736f726c6f676f732f70696e67646f6d2d77686974652d6c6f676f2d67355831547546362e706e67
- https://pypi-camo.freetls.fastly.net/67af7117035e2345bacb5a82e9aa8b5b3e70701d/68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f707970692d6173736574732f73706f6e736f726c6f676f732f73656e7472792d77686974652d6c6f676f2d4a2d6b64742d706e2e706e67
- https://pypi-camo.freetls.fastly.net/b611884ff90435a0575dbab7d9b0d3e60f136466/68747470733a2f2f73746f726167652e676f6f676c65617069732e636f6d2f707970692d6173736574732f73706f6e736f726c6f676f732f737461747573706167652d77686974652d6c6f676f2d5467476c6a4a2d502e706e67

These clickable hyperlinks allow you to view what was extracted from the website you chose to scrape. This first set of code has not been refined but this is a good example that the simple process of extracting images, headers & links.













o	After running the code with different websites, we ran into a website that gave us an error. 
This error is “We've detected unusual activity from your computer network”.
To get rid of this issue I prompted what could be the specific problem associated with receiving this feedback.
The Prompt: “From certain sites we got back "We've detected unusual activity from your computer network", why is this happening”
The Prompt Output with added on solutions:
1.	High frequency request that can cause the website to suspect unusual behavior compared to human browsing patters and the website can flag & block you for this. The solution would be to implement delays between request using ‘time.sleep()’ to mimic natural browsing speed.
2.	Ip address blocking or throttling monitors the number of request coming from one single Ip Address. The solution would be to add rotating Ip A’s which can distribute the request and avoid hitting rate limits form a single IP Address.
3.	Include headers like User-Agent, Accept-Language, and Referer to make requests look like they are coming from a regular browser.
From an ethical standpoint, when implementing these, scrape responsibly respect the rules of the website you’re interacting with.
o	The issue that occurred & was fixed by the solutions above through a step by step problem solving method.
Issue: When trying to scrape this site (https://www.bloomberg.com/) the error that occurred in the results after running the code was “We've detected unusual activity from your computer network”.

o	The changes took that allowed us to successfully scrape this site & potentially opened the door for many other sites as well. **On page 9**



1. Implement delays between requests using time.sleep() or similar methods to mimic natural browsing speed.
2. Include headers like User-Agent, Accept-Language, and Referer to make requests look like they are coming from a regular browser.
3. Manage cookies using sessions with the requests library or similar tools to maintain continuity and reduce the likelihood of detection.
o	Changes in code:-

import requests
from bs4 import BeautifulSoup
import time
import random

def web_scraper(url):
    # Define headers with additional attributes to mimic a browser request
    headers = {
        'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.102 Safari/537.36',
        'Accept-Language': 'en-US,en;q=0.9',
        'Referer': url
    }
    
    # Create a session to handle cookies
    session = requests.Session()
    session.headers.update(headers)

    try:
        # Send a GET request to the website with headers
        response = session.get(url)
        
        # Check if the request was successful
        if response.status_code == 200:
            # Parse the HTML content using Beautiful Soup
            soup = BeautifulSoup(response.text, 'html.parser')
            
            # Extract headlines (e.g., all <h2> tags)
            headlines = [headline.get_text() for headline in soup.find_all('h2')]
            
            # Extract all links (e.g., <a> tags with href attributes)
            links = [a['href'] for a in soup.find_all('a', href=True)]
            
            # Extract images (e.g., <img> tags with src attributes)
            images = [img['src'] for img in soup.find_all('img', src=True)]
            
            # Print extracted data
            print("Headlines:")
            for headline in headlines:
                print(f"- {headline}")
            
            print("\nLinks:")
            for link in links:
                print(f"- {link}")
            
            print("\nImages:")
            for image in images:
                print(f"- {image}")
        else:
            # Print status code and reason for failure
            print(f"Failed to retrieve the page. Status code: {response.status_code} - Reason: {response.reason}")
    
    except requests.exceptions.RequestException as e:
        print(f"An error occurred: {e}")

    # Introduce a random delay after the request
    time.sleep(random.uniform(3, 7))

# Example usage
web_scraper('https://www.bloomberg.com')  # Replace with your target URL


o	The output results after running the code, scraped the site & it gave us the requested headers, links & images



This first overall set of refinement is to entail the problem solving & also to test the scraper by just grabbing simple headlines, links & images from websites in an automated fashion.


First set of 403 errors that came about when I searched on job websites to try to parse html form many sites with specific keywords.
Here is this code & output:

# Import necessary libraries
import httpx
from bs4 import BeautifulSoup
import time
import random
from fake_useragent import UserAgent  # Ensure fake-useragent is installed

# List of job websites
job_websites = [
    "https://stackoverflow.com",
    "https://www.reddit.com",
    "https://www.linkedin.com",
    "https://www.indeed.com",
    "https://www.glassdoor.com",
    "https://www.simplyhired.com"
]

# Keywords for job search
cybersecurity_keywords = [
    "Encryption", "Firewall", "Malware", "Phishing", "Ransomware", 
    "Authentication", "Vulnerability", "Intrusion", "Spyware", 
    "Cyberattack", "Data Breach", "Antivirus", "SSL", "2FA", 
    "Botnet", "Zero-Day", "Penetration Testing"
]

entry_level_keywords = [
    "Cybersecurity Analyst", "Information Security Analyst", 
    "Security Operations Center (SOC) Analyst", "Network Security Associate", 
    "Junior Cybersecurity Specialist", "IT Security Intern", 
    "Cybersecurity Internship", "Entry-Level Security Engineer", 
    "Security Incident Response Analyst", "Vulnerability Assessment Analyst",
    "Threat Intelligence Analyst", "Information Assurance Analyst",
    "Penetration Tester (Entry Level)", "Security Compliance Analyst",
    "Cybersecurity Technician"
]

job_parameters = ["Remote", "Onsite", "Less than 2 years experience"]

# Extra info criteria
extra_info = ["location", "employer", "responsibilities", "key skills required", "posted date"]

# CAPTCHA solving placeholder function
def solve_captcha(sitekey, url):
    # Placeholder for integrating 2Captcha or Anti-Captcha service
    # For example, you would send the sitekey and URL to the CAPTCHA solving service and get a response token
    print(f"Solving CAPTCHA for {url} with sitekey {sitekey}")
    # Simulate solving CAPTCHA with a dummy token
    return "dummy_captcha_token"

# Function to scrape jobs based on keywords and extra info
def scrape_jobs(url, keywords, extra_info=None):
    # Rotate user-agents
    ua = UserAgent()
    headers = {
        'User-Agent': ua.random,
        'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
        'Accept-Language': 'en-US,en;q=0.9',
        'Referer': url,
        'Connection': 'keep-alive',
        'Upgrade-Insecure-Requests': '1',
        'DNT': '1',  # Do Not Track request header
        'Accept-Encoding': 'gzip, deflate, br',
        'Cache-Control': 'no-cache',
        'Pragma': 'no-cache',
        'Sec-Fetch-Site': 'same-origin',  # Security feature for the Origin header
        'Sec-Fetch-Mode': 'navigate',
        'Sec-Fetch-User': '?1',
        'Sec-Fetch-Dest': 'document',
        'Origin': url,  # Origin header to mimic requests from the page itself
        'TE': 'trailers'  # Indicates the transfer encoding
    }

    # Using httpx for better TLS/SSL handling
    with httpx.Client(headers=headers, timeout=10.0, follow_redirects=True, http2=True) as client:
        try:
            response = client.get(url)

            # Check if CAPTCHA challenge is detected
            if "captcha" in response.text.lower():
                print(f"CAPTCHA detected on {url}. Attempting to solve.")
                # Example placeholder for solving CAPTCHA
                # Replace with actual logic for CAPTCHA solving
                solve_captcha("sitekey_example", url) 

            if response.status_code == 200:
                soup = BeautifulSoup(response.text, 'html.parser')

                # Extract relevant information based on keywords
                job_posts = soup.find_all(['h2', 'a', 'p'])  # Adjust tags as needed
                matches = []

                for post in job_posts:
                    text = post.get_text().lower()
                    for keyword in keywords:
                        if keyword.lower() in text:
                            job_info = {
                                'text': text,
                                'link': post.find('a')['href'] if post.find('a') else 'N/A'
                            }

                            # Extract extra information if available
                            for info in extra_info:
                                if info in text:
                                    job_info[info] = text  # Adjust based on exact info structure

                            matches.append(job_info)
                            break

                # Print or save matches
                print(f"Matches from {url}:")
                for match in matches:
                    print(f"- Text: {match['text']}\n  Link: {match['link']}")
                    for key, value in match.items():
                        if key not in ['text', 'link']:
                            print(f"  {key.capitalize()}: {value}")
                    print("\n")

            else:
                print(f"Failed to retrieve {url}. Status code: {response.status_code} - Reason: {response.reason_phrase}")

        except httpx.RequestError as e:
            print(f"An error occurred: {e}")

        # Introduce a random delay after each request to mimic human browsing
        browse_delay = random.uniform(5, 15)  # Increased delay range to mimic browsing
        print(f"Waiting for {browse_delay:.2f} seconds to simulate browsing behavior...")
        time.sleep(browse_delay)

# Example usage
for website in job_websites:
    scrape_jobs(website, cybersecurity_keywords + entry_level_keywords, extra_info)


Output After Running the code:

Matches from https://stackoverflow.com:
Waiting for 7.75 seconds to simulate browsing behavior...
Failed to retrieve https://www.reddit.com. Status code: 403 - Reason: Forbidden
Waiting for 11.96 seconds to simulate browsing behavior...
Matches from https://www.linkedin.com:
Waiting for 8.47 seconds to simulate browsing behavior...
Failed to retrieve https://www.indeed.com. Status code: 403 - Reason: Forbidden
Waiting for 5.31 seconds to simulate browsing behavior...
Failed to retrieve https://www.glassdoor.com. Status code: 403 - Reason: Forbidden
Waiting for 6.02 seconds to simulate browsing behavior...
Failed to retrieve https://www.simplyhired.com. Status code: 403 - Reason: Forbidden
Waiting for 7.48 seconds to simulate browsing behavior...


Resolving this issue all together came about when we Integrate an API into this specific code with the assistance of an AI model. (Jsearch API). This code was restructured & also using specific websites was terminated.

The API:
import http.client

conn = http.client.HTTPSConnection("jsearch.p.rapidapi.com")

headers = {
    'x-rapidapi-key': "072f716e1fmsh1d95c184aa5c087p18909cjsn7bb6a3435ed3",
    'x-rapidapi-host': "jsearch.p.rapidapi.com"
}

conn.request("GET", "/search?query=Node.js%20developer%20in%20New-York%2CUSA&page=1&num_pages=1&date_posted=all", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))

Refactored API code by AI Model:

import http.client
import json

# Function to search for jobs using the JSearch API
def search_jobs(query, location, page=1, num_pages=1, date_posted='all'):
    # Set up the connection and request
    conn = http.client.HTTPSConnection("jsearch.p.rapidapi.com")

    # Replace these values with your own RapidAPI credentials
    headers = {
        'x-rapidapi-key': "072f716e1fmsh1d95c184aa5c087p18909cjsn7bb6a3435ed3",
        'x-rapidapi-host': "jsearch.p.rapidapi.com"
    }

    # Construct the URL with query parameters
    request_url = f"/search?query={query}%20in%20{location}&page={page}&num_pages={num_pages}&date_posted={date_posted}"

    # Make the GET request
    conn.request("GET", request_url, headers=headers)

    # Get the response
    res = conn.getresponse()
    data = res.read()

    # Decode the response
    decoded_data = data.decode("utf-8")

    # Parse the JSON response
    job_results = json.loads(decoded_data)

    return job_results


# Example usage
if __name__ == "__main__":
    query = "Node.js developer"
    location = "New-York,USA"
    page = 1
    num_pages = 1
    date_posted = "all"

    job_listings = search_jobs(query, location, page, num_pages, date_posted)

    # Print the job results
    for job in job_listings.get('data', []):
        print(f"Job Title: {job.get('job_title')}")
        print(f"Company: {job.get('employer_name')}")
        print(f"Location: {job.get('location')}")
        print(f"Posted Date: {job.get('job_posted_at_datetime_utc')}")
        print(f"Link: {job.get('job_apply_link')}\n")


API Integrated with my code:

import http.client
import json
import time
import random
from fake_useragent import UserAgent

# Keywords for job search
cybersecurity_keywords = [
    "Encryption", "Firewall", "Malware", "Phishing", "Ransomware",
    "Authentication", "Vulnerability", "Intrusion", "Spyware",
    "Cyberattack", "Data Breach", "Antivirus", "SSL", "2FA",
    "Botnet", "Zero-Day", "Penetration Testing"
]

entry_level_keywords = [
    "Cybersecurity Analyst", "Information Security Analyst",
    "Security Operations Center (SOC) Analyst", "Network Security Associate",
    "Junior Cybersecurity Specialist", "IT Security Intern",
    "Cybersecurity Internship", "Entry-Level Security Engineer",
    "Security Incident Response Analyst", "Vulnerability Assessment Analyst",
    "Threat Intelligence Analyst", "Information Assurance Analyst",
    "Penetration Tester (Entry Level)", "Security Compliance Analyst",
    "Cybersecurity Technician"
]

job_parameters = ["Remote", "Onsite", "Less than 2 years experience"]

# Extra info criteria
extra_info = ["location", "employer", "responsibilities", "key skills required", "posted date"]

# Function to search for jobs using the JSearch API
def search_jobs(query, location, page=1, num_pages=1, date_posted='all'):
    # Set up the connection and request
    conn = http.client.HTTPSConnection("jsearch.p.rapidapi.com")

    # Replace these values with your own RapidAPI credentials
    headers = {
        'x-rapidapi-key': "072f716e1fmsh1d95c184aa5c087p18909cjsn7bb6a3435ed3",
        'x-rapidapi-host': "jsearch.p.rapidapi.com"
    }

    # Construct the URL with query parameters
    request_url = f"/search?query={query}%20in%20{location}&page={page}&num_pages={num_pages}&date_posted={date_posted}"

    # Make the GET request
    conn.request("GET", request_url, headers=headers)

    # Get the response
    res = conn.getresponse()
    data = res.read()

    # Decode the response
    decoded_data = data.decode("utf-8")

    # Parse the JSON response
    job_results = json.loads(decoded_data)

    return job_results


# Function to scrape jobs using both cybersecurity and entry-level keywords
def scrape_jobs(keywords, location="USA", extra_info=None, page=1, num_pages=1):
    # Rotate user-agents to avoid getting blocked
    ua = UserAgent()
    headers = {
        'User-Agent': ua.random,
        'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
        'Accept-Language': 'en-US,en;q=0.9',
        'Referer': location,
        'Connection': 'keep-alive',
        'Upgrade-Insecure-Requests': '1',
        'DNT': '1',  # Do Not Track request header
        'Accept-Encoding': 'gzip, deflate, br',
        'Cache-Control': 'no-cache',
        'Pragma': 'no-cache',
        'Sec-Fetch-Site': 'same-origin',  # Security feature for the Origin header
        'Sec-Fetch-Mode': 'navigate',
        'Sec-Fetch-User': '?1',
        'Sec-Fetch-Dest': 'document',
        'Origin': location,  # Origin header to mimic requests from the page itself
        'TE': 'trailers'  # Indicates the transfer encoding
    }

    # Iterate through the keywords and search for jobs
    for keyword in keywords:
        print(f"Searching for jobs with keyword: {keyword} in {location}")

        # Call the search_jobs function with the specific keyword
        job_listings = search_jobs(query=keyword, location=location, page=page, num_pages=num_pages)

        # Check if job results exist
        if job_listings.get('data'):
            for job in job_listings['data']:
                job_info = {
                    'title': job.get('job_title'),
                    'company': job.get('employer_name'),
                    'location': job.get('location'),
                    'posted_date': job.get('job_posted_at_datetime_utc'),
                    'apply_link': job.get('job_apply_link')
                }

                # Display additional information if requested
                if extra_info:
                    for info in extra_info:
                        if job_info.get(info):
                            print(f"{info.capitalize()}: {job_info.get(info)}")

                # Print the job details
                print(f"Job Title: {job_info['title']}")
                print(f"Company: {job_info['company']}")
                print(f"Location: {job_info['location']}")
                print(f"Posted Date: {job_info['posted_date']}")
                print(f"Apply Link: {job_info['apply_link']}\n")
        else:
            print(f"No job results found for keyword: {keyword}")

        # Introduce a random delay to mimic human browsing
        browse_delay = random.uniform(5, 15)
        print(f"Waiting for {browse_delay:.2f} seconds before the next search...")
        time.sleep(browse_delay)


# Example usage
if __name__ == "__main__":
    all_keywords = cybersecurity_keywords + entry_level_keywords
    scrape_jobs(all_keywords, location="USA", extra_info=extra_info, page=1, num_pages=1)

Output From This Successful Scrape (Only 3 outputs displayed here for example out of many that it produced) 

Searching for jobs with keyword: Encryption in USA
Job Title: Data Security Encryption
Company: 300 U.S. Bank National Association
Location: None
Posted Date: 2024-08-15T22:08:00.000Z
Apply Link: https://www.ziprecruiter.com/c/300-U.S.-Bank-National-Association/Job/Data-Security-Encryption/-in-Charlotte,NC?jid=daf232452a92409e&utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic

Job Title: Encryption Engineering Team Lead
Company: 001 Manufacturers and Traders Trust Co
Location: None
Posted Date: 2024-08-10T02:02:00.000Z
Apply Link: https://www.ziprecruiter.com/c/001-Manufacturers-and-Traders-Trust-Co/Job/Encryption-Engineering-Team-Lead/-in-Buffalo,NY?jid=36f289ae28d053a1&utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic

Waiting for 11.82 seconds before the next search...
Searching for jobs with keyword: Firewall in USA
Job Title: Infrastructure Security Engineer (Firewall Security Platform)
Company: PNC
Location: None
Posted Date: 2024-09-06T00:00:00.000Z
Apply Link: https://careers.pnc.com/global/en/job/R172364/Infrastructure-Security-Engineer-Firewall-Security-Platform?utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic


I instantly realized that this code goes through the 40 keywords one by one and it pick up multiple jobs from each & soon this with cause the API to go over its monthly limit.

I combined the 15 keywords in a string with other parameters but later on to find out this was not necessary.

import http.client
import json
import time
import random
from fake_useragent import UserAgent

# New list with the provided combined keyword strings
cybersecurity_keywords = [
    "Cybersecurity Analyst skills required less than 2 years experience",
    "Information Security Analyst skills required less than 2 years experience",
    "Security Operations Center (SOC) Analyst skills required less than 2 years experience",
    "Network Security Associate skills required less than 2 years experience",
    "Junior Cybersecurity Specialist skills required less than 2 years experience",
    "IT Security Intern skills required less than 2 years experience",
    "Cybersecurity Internship skills required less than 2 years experience",
    "Entry-Level Security Engineer skills required less than 2 years experience",
    "Security Incident Response Analyst skills required less than 2 years experience",
    "Vulnerability Assessment Analyst skills required less than 2 years experience",
    "Threat Intelligence Analyst skills required less than 2 years experience",
    "Information Assurance Analyst skills required less than 2 years experience",
    "Penetration Tester (Entry Level) skills required less than 2 years experience",
    "Security Compliance Analyst skills required less than 2 years experience",
    "Cybersecurity Technician skills required less than 2 years experience"
]

# Function to search for jobs using the JSearch API
def search_jobs(query, location, page=1, num_pages=1, date_posted='all'):
    # Set up the connection and request
    conn = http.client.HTTPSConnection("jsearch.p.rapidapi.com")

    # Replace these values with your own RapidAPI credentials
    headers = {
        'x-rapidapi-key': "072f716e1fmsh1d95c184aa5c087p18909cjsn7bb6a3435ed3",
        'x-rapidapi-host': "jsearch.p.rapidapi.com"
    }

    # Construct the URL with query parameters
    request_url = f"/search?query={query.replace(' ', '%20')}&location={location}&page={page}&num_pages={num_pages}&date_posted={date_posted}"

    # Make the GET request
    conn.request("GET", request_url, headers=headers)

    # Get the response
    res = conn.getresponse()
    data = res.read()

    # Decode the response
    decoded_data = data.decode("utf-8")

    # Parse the JSON response
    job_results = json.loads(decoded_data)

    return job_results


# Function to scrape jobs using the combined query strings
def scrape_jobs(keywords_list, location="USA", extra_info=None, page=1, num_pages=1):
    # Rotate user-agents to avoid getting blocked
    ua = UserAgent()
    headers = {
        'User-Agent': ua.random,
        'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
        'Accept-Language': 'en-US,en;q=0.9',
        'Referer': location,
        'Connection': 'keep-alive',
        'Upgrade-Insecure-Requests': '1',
        'DNT': '1',  # Do Not Track request header
        'Accept-Encoding': 'gzip, deflate, br',
        'Cache-Control': 'no-cache',
        'Pragma': 'no-cache'
    }

    # Iterate through the combined keyword strings and search for jobs
    for keywords in keywords_list:
        print(f"Searching for jobs with combined keywords: {keywords} in {location}")

        # Call the search_jobs function with the combined keyword query
        job_listings = search_jobs(query=keywords, location=location, page=page, num_pages=num_pages)

        # Check if job results exist
        if job_listings.get('data'):
            for job in job_listings['data']:
                job_info = {
                    'title': job.get('job_title'),
                    'company': job.get('employer_name'),
                    'location': job.get('location'),
                    'posted_date': job.get('job_posted_at_datetime_utc'),
                    'apply_link': job.get('job_apply_link')
                }

                # Display additional information if requested
                if extra_info:
                    for info in extra_info:
                        if job_info.get(info):
                            print(f"{info.capitalize()}: {job_info.get(info)}")

                # Print the job details
                print(f"Job Title: {job_info['title']}")
                print(f"Company: {job_info['company']}")
                print(f"Location: {job_info['location']}")
                print(f"Posted Date: {job_info['posted_date']}")
                print(f"Apply Link: {job_info['apply_link']}\n")
        else:
            print(f"No job results found for the combined query: {keywords}")

        # Introduce a random delay to mimic human browsing
        browse_delay = random.uniform(5, 15)
        print(f"Waiting for {browse_delay:.2f} seconds before the next search...")
        time.sleep(browse_delay)


# Example usage
if __name__ == "__main__":
    # Iterate through the list of combined keyword strings
    scrape_jobs(cybersecurity_keywords, location="USA", extra_info=["location", "employer", "posted date"], page=1, num_pages=1)

2 Example outputs out of many:

Searching for jobs with combined keywords: Cybersecurity Analyst skills required less than 2 years experience in USA
Job Title: Lead Security Analyst
Company: City of Alexandria
Location: None
Posted Date: 2024-05-29T21:00:00.000Z
Apply Link: https://www.governmentjobs.com/careers/alexandria/jobs/4522993/lead-security-analyst?utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic

Job Title: Cyber security analyst
Company: CareFirst BlueCross BlueShield
Location: None
Posted Date: 2024-09-09T00:00:00.000Z
Apply Link: https://www.talent.com/view?id=554fd2e88f98&utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic

I refined the code to extract more info from these website(skills required, responsibilities, & experience)

The code:

import http.client
import json
import time
import random
from fake_useragent import UserAgent

# New list with the provided combined keyword strings
cybersecurity_keywords = [
    "Cybersecurity Analyst skills required less than 2 years experience",
    "Information Security Analyst skills required less than 2 years experience",
    "Security Operations Center (SOC) Analyst skills required less than 2 years experience",
    "Network Security Associate skills required less than 2 years experience",
    "Junior Cybersecurity Specialist skills required less than 2 years experience",
    "IT Security Intern skills required less than 2 years experience",
    "Cybersecurity Internship skills required less than 2 years experience",
    "Entry-Level Security Engineer skills required less than 2 years experience",
    "Security Incident Response Analyst skills required less than 2 years experience",
    "Vulnerability Assessment Analyst skills required less than 2 years experience",
    "Threat Intelligence Analyst skills required less than 2 years experience",
    "Information Assurance Analyst skills required less than 2 years experience",
    "Penetration Tester (Entry Level) skills required less than 2 years experience",
    "Security Compliance Analyst skills required less than 2 years experience",
    "Cybersecurity Technician skills required less than 2 years experience"
]

# Function to search for jobs using the JSearch API
def search_jobs(query, location, page=1, num_pages=1, date_posted='all'):
    # Set up the connection and request
    conn = http.client.HTTPSConnection("jsearch.p.rapidapi.com")

    # Replace these values with your own RapidAPI credentials
    headers = {
        'x-rapidapi-key': "072f716e1fmsh1d95c184aa5c087p18909cjsn7bb6a3435ed3",  # Enter your own RapidAPI key here
        'x-rapidapi-host': "jsearch.p.rapidapi.com"
    }

    # Construct the URL with query parameters
    request_url = f"/search?query={query.replace(' ', '%20')}&location={location}&page={page}&num_pages={num_pages}&date_posted={date_posted}"

    # Make the GET request
    conn.request("GET", request_url, headers=headers)

    # Get the response
    res = conn.getresponse()
    data = res.read()

    # Decode the response
    decoded_data = data.decode("utf-8")

    # Parse the JSON response
    job_results = json.loads(decoded_data)

    return job_results


# Function to scrape jobs using the combined query strings
def scrape_jobs(keywords_list, location="USA", extra_info=None, page=1, num_pages=1):
    # Rotate user-agents to avoid getting blocked
    ua = UserAgent()
    headers = {
        'User-Agent': ua.random,
        'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
        'Accept-Language': 'en-US,en;q=0.9',
        'Referer': location,
        'Connection': 'keep-alive',
        'Upgrade-Insecure-Requests': '1',
        'DNT': '1',  # Do Not Track request header
        'Accept-Encoding': 'gzip, deflate, br',
        'Cache-Control': 'no-cache',
        'Pragma': 'no-cache'
    }

    # Iterate through the combined keyword strings and search for jobs
    for keywords in keywords_list:
        print(f"Searching for jobs with combined keywords: {keywords} in {location}")

        # Call the search_jobs function with the combined keyword query
        job_listings = search_jobs(query=keywords, location=location, page=page, num_pages=num_pages)

        # Check if job results exist
        if job_listings.get('data'):
            for job in job_listings['data']:
                job_info = {
                    'title': job.get('job_title', 'N/A'),
                    'company': job.get('employer_name', 'N/A'),
                    'location': job.get('location', 'N/A'),
                    'posted_date': job.get('job_posted_at_datetime_utc', 'N/A'),
                    'apply_link': job.get('job_apply_link', 'N/A'),
                    'skills_required': ', '.join(job.get('job_highlights', {}).get('Qualifications', ['Not specified'])),
                    'responsibilities': ', '.join(job.get('job_highlights', {}).get('Responsibilities', ['Not specified'])),
                    'experience': job.get('job_required_experience', 'Not specified')
                }

                # Display additional information if requested
                if extra_info:
                    for info in extra_info:
                        if job_info.get(info):
                            print(f"{info.capitalize()}: {job_info.get(info)}")

                # Print the job details
                print(f"Job Title: {job_info['title']}")
                print(f"Company: {job_info['company']}")
                print(f"Location: {job_info['location']}")
                print(f"Posted Date: {job_info['posted_date']}")
                print(f"Apply Link: {job_info['apply_link']}")
                print(f"Skills Required: {job_info['skills_required']}")
                print(f"Responsibilities: {job_info['responsibilities']}")
                print(f"Experience: {job_info['experience']}\n")
        else:
            print(f"No job results found for the combined query: {keywords}")

        # Introduce a random delay to mimic human browsing
        browse_delay = random.uniform(5, 15)
        print(f"Waiting for {browse_delay:.2f} seconds before the next search...")
        time.sleep(browse_delay)


# Example usage
if __name__ == "__main__":
    # Iterate through the list of combined keyword strings
    scrape_jobs(cybersecurity_keywords, location="USA", extra_info=["location", "employer", "posted date"], page=1, num_pages=1)

The output(successful on skills requied & responsibilities but not experience:

Searching for jobs with combined keywords: Cybersecurity Analyst skills required less than 2 years experience in USA
Location: N/A
Job Title: Cyber Security Analyst
Company: Leidos
Location: N/A
Posted Date: 2024-07-14T10:13:50.000Z
Apply Link: https://careers.leidos.com/jobs/14523031-cyber-security-analyst?utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic
-Skills Required: Demonstrated understanding of TCP/IP, common networking ports and protocols, traffic flow, system administration, OSI model, defense-in-depth and common security elements, Motivated self-starter with strong written and verbal communication skills, and the ability to create complex technical reports on analytic findings, DoD 8570 IAT level II or higher certification such as CompTIA Security+ CE, ISC2 SSCP, SANS GSEC prior to starting, DoD 8570 CSSP-A level Certification such as CEH, CySA+, GCIA or other certification is required within 180 days of hire, Demonstrated commitment to training, self-study and maintaining proficiency in the technical cyber security domain and an ability to think and work independently, Bachelor's degree and less than 2+ years of prior relevant experience; additional work experience or Cyber courses/certifications may be substituted in lieu of degree, Strong analytical and troubleshooting skills, Willing to perform shift work, Must be a US Citizen, Must have an active DoD TOP Secret security w/ SCI clearance eligibility, Experience and proficiency with any of the following: Anti-Virus, HIPS/HBSS, IDS/IPS, Full Packet Capture, Network Forensics, Experience with malware analysis concepts and methods, Unix/Linux command line experience, Scripting and programming experience, Familiarity or experience in Intelligence Driven Defense and/or Cyber Kill Chain methodology, Existing 8570 CSSP Analyst Certifications (CEH), CySA+ etc
-Responsibilities: This position provides 24x7 cybersecurity monitoring and analysis services for Department of Defense networks above the SECRET level, This includes performing real-time cyber threat intelligence analysis, correlating actionable security events, performing network traffic analysis using raw packet data, and participating in the coordination of resources during the incident response process, Review DoD and open source intelligence for threats and to identify Indicators of Compromise (IOCs) and integrate those into sensors and SIEMs, Utilize alerts from endpoints, IDS/IPS, netflow, and custom sensors to identify compromises on customer networks/endpoints, Review massive log files, pivot between data sets, and correlate evidence for incident investigations, Triage alerts to identify malicious actors on customer networks, Report incidents to customers and USCYBERCOM
-Experience: {'no_experience_required': 'false', 'required_experience_in_months': '96', 'experience_mentioned': 'true', 'experience_preferred': 'false'}

This "experience" output was caused by it printing a dictionary instead of clean code & it was also formatted in months. Later on this will be formatted again with a limit of 24months (2 years experience).

The Code:
import http.client
import json
import time
import random
from fake_useragent import UserAgent

# New list with the provided combined keyword strings
cybersecurity_keywords = [
    "Cybersecurity Analyst skills required less than 2 years experience",
    "Information Security Analyst skills required less than 2 years experience",
    "Security Operations Center (SOC) Analyst skills required less than 2 years experience",
    "Network Security Associate skills required less than 2 years experience",
    "Junior Cybersecurity Specialist skills required less than 2 years experience",
    "IT Security Intern skills required less than 2 years experience",
    "Cybersecurity Internship skills required less than 2 years experience",
    "Entry-Level Security Engineer skills required less than 2 years experience",
    "Security Incident Response Analyst skills required less than 2 years experience",
    "Vulnerability Assessment Analyst skills required less than 2 years experience",
    "Threat Intelligence Analyst skills required less than 2 years experience",
    "Information Assurance Analyst skills required less than 2 years experience",
    "Penetration Tester (Entry Level) skills required less than 2 years experience",
    "Security Compliance Analyst skills required less than 2 years experience",
    "Cybersecurity Technician skills required less than 2 years experience"
]

# Function to search for jobs using the JSearch API
def search_jobs(query, location, page=1, num_pages=1, date_posted='all'):
    # Set up the connection and request
    conn = http.client.HTTPSConnection("jsearch.p.rapidapi.com")

    # Replace these values with your own RapidAPI credentials
    headers = {
        'x-rapidapi-key': "072f716e1fmsh1d95c184aa5c087p18909cjsn7bb6a3435ed3",  # Enter your own RapidAPI key here
        'x-rapidapi-host': "jsearch.p.rapidapi.com"
    }

    # Construct the URL with query parameters
    request_url = f"/search?query={query.replace(' ', '%20')}&location={location}&page={page}&num_pages={num_pages}&date_posted={date_posted}"

    # Make the GET request
    conn.request("GET", request_url, headers=headers)

    # Get the response
    res = conn.getresponse()
    data = res.read()

    # Decode the response
    decoded_data = data.decode("utf-8")

    # Parse the JSON response
    job_results = json.loads(decoded_data)

    return job_results


# Function to scrape jobs using the combined query strings
def scrape_jobs(keywords_list, location="USA", extra_info=None, page=1, num_pages=1):
    # Rotate user-agents to avoid getting blocked
    ua = UserAgent()
    headers = {
        'User-Agent': ua.random,
        'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
        'Accept-Language': 'en-US,en;q=0.9',
        'Referer': location,
        'Connection': 'keep-alive',
        'Upgrade-Insecure-Requests': '1',
        'DNT': '1',  # Do Not Track request header
        'Accept-Encoding': 'gzip, deflate, br',
        'Cache-Control': 'no-cache',
        'Pragma': 'no-cache'
    }

    # Iterate through the combined keyword strings and search for jobs
    for keywords in keywords_list:
        print(f"Searching for jobs with combined keywords: {keywords} in {location}")

        # Call the search_jobs function with the combined keyword query
        job_listings = search_jobs(query=keywords, location=location, page=page, num_pages=num_pages)

        # Check if job results exist
        if job_listings.get('data'):
            for job in job_listings['data']:
                experience_info = job.get('job_required_experience', {})
                required_experience_months = experience_info.get('required_experience_in_months', 'Not specified')
                experience_required = experience_info.get('experience_mentioned', 'Not specified')

                job_info = {
                    'title': job.get('job_title', 'N/A'),
                    'company': job.get('employer_name', 'N/A'),
                    'location': job.get('location', 'N/A'),
                    'posted_date': job.get('job_posted_at_datetime_utc', 'N/A'),
                    'apply_link': job.get('job_apply_link', 'N/A'),
                    'experience': f"{required_experience_months} months of experience required" if experience_required == "true" else "Experience not mentioned",
                    'skills_required': ', '.join(job.get('job_highlights', {}).get('Qualifications', ['Not specified'])),
                    'responsibilities': ', '.join(job.get('job_highlights', {}).get('Responsibilities', ['Not specified']))
                }

                # Display additional information if requested
                if extra_info:
                    for info in extra_info:
                        if info in job_info:
                            print(f"{info.capitalize()}: {job_info[info]}")

                # Print the job details
                print(f"Job Title: {job_info['title']}")
                print(f"Company: {job_info['company']}")
                print(f"Location: {job_info['location']}")
                print(f"Posted Date: {job_info['posted_date']}")
                print(f"Apply Link: {job_info['apply_link']}")
                print(f"Skills Required: {job_info['skills_required']}")
                print(f"Responsibilities: {job_info['responsibilities']}")
                print(f"Experience: {job_info['experience']}\n")
        else:
            print(f"No job results found for the combined query: {keywords}")

        # Introduce a random delay to mimic human browsing
        browse_delay = random.uniform(5, 15)
        print(f"Waiting for {browse_delay:.2f} seconds before the next search...")
        time.sleep(browse_delay)


# Example usage
if __name__ == "__main__":
    # Iterate through the list of combined keyword strings
    scrape_jobs(cybersecurity_keywords, location="USA", extra_info=["location"], page=1, num_pages=1)

Code Output:

Searching for jobs with combined keywords: Cybersecurity Analyst skills required less than 2 years experience in USA
Location: N/A
Job Title: Lead Security Analyst
Company: City of Alexandria
Location: N/A
Posted Date: 2024-05-29T21:00:00.000Z
Apply Link: https://www.governmentjobs.com/careers/alexandria/jobs/4522993/lead-security-analyst?utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic
Skills Required: You should have a demonstrated ability of being able to work independently, as well as a history of establishing and maintaining effective working relationships with coworkers, representatives of other departments and agencies, and the public, You must be able to communicate clearly and effectively, both verbally and in writing, as well as being able to mentor junior staff, You should be able to show proactivity in continuously improving your job knowledge and technical and functional skills through training opportunities and self-study, Our ideal candidate will have considerable hands-on experience in all aspects of cybersecurity, and an ability to lead, manage, and communicate, Four-Year College Degree with completion of college courses in computer science or related field; five years of experience as a Computer Programmer Analyst III or Network Engineer II including one year as an Information Security Analyst or Engineer, also to include three years of experience in project and contract management; or any equivalent combination of experience and training which provides the required knowledge, skills and abilities, Recent technical experience within the past five years demonstrating a comprehensive knowledge of information security and risk management and technology (audit compliance, regulatory compliance, business continuity and disaster recovery, vulnerability management, configuration management, web application security, intrusion detection and prevention systems, firewalls, and endpoint security), Recent technical experience within the past five years demonstrating a comprehensive knowledge of security administration in a Windows-based network environment, Recent experience within the past five years demonstrating a comprehensive knowledge of information protection standards, guidelines, and applied procedures (i.e., industry "best practices"), Technical experience within the past 10 years demonstrating a comprehensive knowledge of server administration as applied to network and internet security, Good working knowledge of industry standard security controls, NIST 800-53, SANS 20 controls, CIS 18 Critical Controls, NIST Cybersecurity Framework, ISO 27002 Standard, and PCI-DSS, Experience within the past 10 years demonstrating a comprehensive knowledge of business needs coupled with the ability to establish and maintain a high level of customer trust and confidence in the security team's concern for customers, This position requires the successful completion of pre-employment checks including but not limited to a criminal background and drug screening
Responsibilities: ITS provides technology services and solutions to City departments to enhance service delivery, ITS aligns its work with City needs by providing leadership, resources, expertise, and products that enable departments to better serve the City’s residents, businesses, and visitors, This position reports directly to the Chief Information Security Officer (CISO) and uses industry best practices to oversee the implementation of all security policies as directed by the CISO, and enforces the City’s enterprise cybersecurity through policy, architecture, technical and functional administration, and training, The Lead Security Analyst will also lead in selecting, configuring, communicating, and implementing cybersecurity solutions and security controls to identify and reduce IT risk, The Lead Security Analyst performs two core functions for the enterprise, The first is the day-to-day operations of the in-place security solutions while the second is the identification, investigation, and resolution of security breaches detected by those systems, Secondary tasks may include involvement in the implementation of new security solutions, participation in the creation and or maintenance of policies, standards, baselines, guidelines, and procedures as well as conducting vulnerability audits and assessments, The Lead Security Analyst is expected to be fully aware of the enterprise’s security goals as established by its stated policies, procedures, and guidelines and to actively work towards upholding those goals, As the Lead Security Analyst your effort will be focused on all aspects of City-wide IT cybersecurity, from developing cybersecurity plans and strategies to preventing and mitigating cyber-attacks, Develop, maintain, and matures risk and compliance reporting and alerting as well as SOC (security operations center) best practices and standard operating procedure documentation, Improve threat awareness through continuous development and improvement of processes including network vulnerability scanning, security information event management (SIEM) system, Threat detection and response, IT governance risk and control management and assessment, IPS/IDS systems, and other applications, Working service tickets within defined response time to completion, Help design, build, process prove and support workflows to the success of defined business goals, Participate as a respectful, thoughtful, listening and contributing member of committees and projects and working groups, Provides operational oversight, including project management, for all threat and vulnerability management functions, Supports the CISO and fellow ITS Security team members in responsibilities including project performance, incident response management, and other functions as needed, Shares in assuming CISO role and responsibility in the absence of the CISO, Ensuring compliance to City, industry and government regulations, policies, standards and procedures, Responding to internal and external audits, Work as an ITS Security team member with various cross-functional and technical teams to ensure effectiveness in measuring and managing risk appropriate for the City of Alexandria risk tolerance, Provide clear and timely analysis and reporting, Participate in the planning and design of an enterprise business continuity plan and disaster recovery plan, under the direction of the CISO, where appropriate, Maintain up-to-date detailed knowledge of the cybersecurity industry including awareness of new or revised security solutions, improved security processes, and the development of new attacks and threat vectors, Recommend additional security solutions or enhancements to existing security solutions to improve overall enterprise security, Assist in the review, selection, deployment, integration, and initial configuration of all new security solutions and of any enhancements to existing security solutions in accordance with standard best operating procedures generically and the enterprise’s security documents specifically, Maintain up-to-date baselines for the secure configuration and operations of all in-place devices, whether they be under direct control (i.e. security tools) or not (e.g. workstations, servers, network devices), Interpret the implications of that activity and devise plans for appropriate resolution, Participate in the design and execution of vulnerability assessments, penetration tests, and security audits, Participates in incident response work, Performing other duties as assigned
-Experience: 60 months of experience required

Looking at the output above it is clear to see some duplication in the headers, this issue was fixed immediately by removing the redundant printing of 'location' because it was already listed in extra_info variable and only printing it once.

The code:

import http.client
import json
import time
import random
from fake_useragent import UserAgent

# New list with the provided combined keyword strings
cybersecurity_keywords = [
    "Cybersecurity Analyst skills required less than 2 years experience",
    "Information Security Analyst skills required less than 2 years experience",
    "Security Operations Center (SOC) Analyst skills required less than 2 years experience",
    "Network Security Associate skills required less than 2 years experience",
    "Junior Cybersecurity Specialist skills required less than 2 years experience",
    "IT Security Intern skills required less than 2 years experience",
    "Cybersecurity Internship skills required less than 2 years experience",
    "Entry-Level Security Engineer skills required less than 2 years experience",
    "Security Incident Response Analyst skills required less than 2 years experience",
    "Vulnerability Assessment Analyst skills required less than 2 years experience",
    "Threat Intelligence Analyst skills required less than 2 years experience",
    "Information Assurance Analyst skills required less than 2 years experience",
    "Penetration Tester (Entry Level) skills required less than 2 years experience",
    "Security Compliance Analyst skills required less than 2 years experience",
    "Cybersecurity Technician skills required less than 2 years experience"
]

# Function to search for jobs using the JSearch API
def search_jobs(query, location, page=1, num_pages=1, date_posted='all'):
    # Set up the connection and request
    conn = http.client.HTTPSConnection("jsearch.p.rapidapi.com")

    # Replace these values with your own RapidAPI credentials
    headers = {
        'x-rapidapi-key': "YOUR_RAPIDAPI_KEY",  # Enter your own RapidAPI key here
        'x-rapidapi-host': "jsearch.p.rapidapi.com"
    }

    # Construct the URL with query parameters
    request_url = f"/search?query={query.replace(' ', '%20')}&location={location}&page={page}&num_pages={num_pages}&date_posted={date_posted}"

    # Make the GET request
    conn.request("GET", request_url, headers=headers)

    # Get the response
    res = conn.getresponse()
    data = res.read()

    # Decode the response
    decoded_data = data.decode("utf-8")

    # Parse the JSON response
    job_results = json.loads(decoded_data)

    return job_results


# Function to scrape jobs using the combined query strings
def scrape_jobs(keywords_list, location="USA", extra_info=None, page=1, num_pages=1):
    # Rotate user-agents to avoid getting blocked
    ua = UserAgent()
    headers = {
        'User-Agent': ua.random,
        'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
        'Accept-Language': 'en-US,en;q=0.9',
        'Referer': location,
        'Connection': 'keep-alive',
        'Upgrade-Insecure-Requests': '1',
        'DNT': '1',  # Do Not Track request header
        'Accept-Encoding': 'gzip, deflate, br',
        'Cache-Control': 'no-cache',
        'Pragma': 'no-cache'
    }

    # Iterate through the combined keyword strings and search for jobs
    for keywords in keywords_list:
        print(f"Searching for jobs with combined keywords: {keywords} in {location}")

        # Call the search_jobs function with the combined keyword query
        job_listings = search_jobs(query=keywords, location=location, page=page, num_pages=num_pages)

        # Check if job results exist
        if job_listings.get('data'):
            for job in job_listings['data']:
                experience_info = job.get('job_required_experience', {})
                required_experience_months = experience_info.get('required_experience_in_months', 'Not specified')
                experience_required = experience_info.get('experience_mentioned', 'Not specified')

                job_info = {
                    'title': job.get('job_title', 'N/A'),
                    'company': job.get('employer_name', 'N/A'),
                    'location': job.get('location', 'N/A'),
                    'posted_date': job.get('job_posted_at_datetime_utc', 'N/A'),
                    'apply_link': job.get('job_apply_link', 'N/A'),
                    'experience': f"{required_experience_months} months of experience required" if experience_required == "true" else "Experience not mentioned",
                    'skills_required': ', '.join(job.get('job_highlights', {}).get('Qualifications', ['Not specified'])),
                    'responsibilities': ', '.join(job.get('job_highlights', {}).get('Responsibilities', ['Not specified']))
                }

                # Display additional information if requested
                if extra_info:
                    for info in extra_info:
                        if info in job_info and job_info[info] != 'N/A':
                            print(f"{info.capitalize()}: {job_info[info]}")

                # Print the job details
                print(f"Job Title: {job_info['title']}")
                print(f"Company: {job_info['company']}")
                print(f"Location: {job_info['location']}")
                print(f"Posted Date: {job_info['posted_date']}")
                print(f"Apply Link: {job_info['apply_link']}")
                print(f"Skills Required: {job_info['skills_required']}")
                print(f"Responsibilities: {job_info['responsibilities']}")
                print(f"Experience: {job_info['experience']}\n")
        else:
            print(f"No job results found for the combined query: {keywords}")

        # Introduce a random delay to mimic human browsing
        browse_delay = random.uniform(5, 15)
        print(f"Waiting for {browse_delay:.2f} seconds before the next search...")
        time.sleep(browse_delay)


# Example usage
if __name__ == "__main__":
    # Iterate through the list of combined keyword strings
    scrape_jobs(cybersecurity_keywords, location="USA", extra_info=["location", "company", "posted_date", "experience", "skills_required", "responsibilities"], page=1, num_pages=1)
)

The output, 2 of many:
Job Title: It security analyst
Company: Indus Valley
Location: N/A
Posted Date: 2024-09-08T00:00:00.000Z
Apply Link: https://www.talent.com/view?id=8c2baf5e92c0&utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic
Skills Required: Top Skills with Years of Experience, Experience in the IT industry analyzing and applying information security principles and practices Required : 1 Year, Experience reviewing IT systems / applications plus basic knowledge of networking components and various operating systems Required : 1 Year, Experience analyzing the applicable NIST Special Publications 800-37 Revision 1, 800-53 Revision 3,4 or 5, and 800-53A Revision 1, CISSP, CISA, PMP and / or Security+ certification - Nice to have - Security+ certification will be required within 6 weeks of starting, Experience working with software vendors to implement security controls Nice to have, Experience working independently and in a team environment, Strong written and verbal communication skills including the ability to explain technical matters to a non-technical audience, Flexibility to adjust quickly to multiple demands, shifting priorities, ambiguity, and rapid change
Responsibilities: Detailed Job Duties : The IT Security Analyst is responsible for completing and maintaining system security plans (SSP) for new and existing systems, This requires close coordination with IT project teams, business and enterprise security representatives, and product owners, to establish and maintain processes and controls for security vulnerability remediation, Create system security plans (SSP) for new applications in alignment with the Secure Application Development Life Cycle (SADLC) and Michigan Security Accreditation Process (MiSAP), Continuously monitor plans of action and milestones (POA&M) and corrective action plans (CAP) as they relate to the SSPs in collaboration with the MDOT Enterprise Information Management (EIM) office, Validate respective SSPs to ensure NIST control requirements are met, uthor recommendations associated with your findings on how to improve the customer's security posture in accordance with SOM PSP & NIST controls, ssist team members and vendors with proper artifact collection to satisfy assessment requirements
Experience: 24 months of experience required

Waiting for 7.63 seconds before the next search...
Searching for jobs with combined keywords: IT Security Intern skills required less than 2 years experience in USA
No job results found for the combined query: IT Security Intern skills required less than 2 years experience
Waiting for 7.31 seconds before the next search...
Searching for jobs with combined keywords: Cybersecurity Internship skills required less than 2 years experience in USA
Job Title: Information Security Engineer - Undergraduate Intern
Company: Intel Corp.
Location: N/A
Posted Date: 2024-07-27T00:00:00.000Z
Apply Link: https://www.jobtrees.com/postid/d190c244e2a7c0f883e6a1955ff6bb48?utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic
Skills Required: We are looking for an undergraduate student in their 3rd or 4th year of college who is highly motivated and willing to work part time (20 hours per week) for 6 months and further develop their information security skills, Strong oral and written communication skills, presentation skills, Analytical and problem-solving skills, Be willing to work in a dynamic and team-oriented environment and be comfortable with working in a virtual/remote environment, Customer service and stakeholder management skills, including experience in setting and managing user and stakeholder expectations, You must possess the below minimum qualifications to be initially considered for this position, Experience listed below would be obtained through a combination of your schoolwork/classes/research and/or relevant previous job and/or internship experiences, STEM contributing position, or (2) a STEM position that only requires a bachelor's degree and less than three years' experience, Must be pursuing a Bachelor's degree in Computer Science/Engineering, Cyber/Information Security, Mathematics/Statistics, or other science/engineering related field, Information security models and concepts, Cloud Computing and Cloud Security Components, CISSP)
Responsibilities: Managing and maintain security compliance, for systems and applications, Assisting with system automation, upgrades, integration with various systems, applications, and data sources, Assisting with automation deployment, application configuration management and related continuous integration, delivery, and management processes, We are looking for aspiring Information Security professionals who support key projects and initiatives
Experience: 3 months of experience required
 

As you can clearly see form the code above, there is unwanted prints in the output "waiting 7.13 seconds before next search". The output needs to be cleaned before exporting it to a csv by simply tweaking the code not to print that statement into the output.

The code:

import http.client
import json
import time
import random
from fake_useragent import UserAgent

# New list with the provided instead of combined strings
cybersecurity_keywords = [
    "Network Security",
    "Penetration Testing",
    "Incident Response",
    "Threat Intelligence",
    "Vulnerability Assessment",
    "Malware Analysis",
    "Risk Management",
    "Security Operations",
    "Encryption",
    "Identity and Access Management",
    "Security Information and Event Management (SIEM)",
    "Firewall Management",
    "Cybersecurity Compliance",
    "Cloud Security",
    "Data Loss Prevention"
]

# Function to search for jobs using the JSearch API
def search_jobs(query, location, page=1, num_pages=1, date_posted='all'):
    # Set up the connection and request
    conn = http.client.HTTPSConnection("jsearch.p.rapidapi.com")

    # Replace these values with your own RapidAPI credentials
    headers = {
        'x-rapidapi-key': "072f716e1fmsh1d95c184aa5c087p18909cjsn7bb6a3435ed3",  # Enter your own RapidAPI key here
        'x-rapidapi-host': "jsearch.p.rapidapi.com"
    }

    # Construct the URL with query parameters
    request_url = f"/search?query={query.replace(' ', '%20')}&location={location}&page={page}&num_pages={num_pages}&date_posted={date_posted}"

    # Make the GET request
    conn.request("GET", request_url, headers=headers)

    # Get the response
    res = conn.getresponse()
    data = res.read()

    # Decode the response
    decoded_data = data.decode("utf-8")

    # Parse the JSON response
    job_results = json.loads(decoded_data)

    return job_results


# Function to scrape jobs using the combined query strings
def scrape_jobs(keywords_list, location="USA", extra_info=None, page=1, num_pages=1):
    # Rotate user-agents to avoid getting blocked
    ua = UserAgent()
    headers = {
        'User-Agent': ua.random,
        'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
        'Accept-Language': 'en-US,en;q=0.9',
        'Referer': location,
        'Connection': 'keep-alive',
        'Upgrade-Insecure-Requests': '1',
        'DNT': '1',  # Do Not Track request header
        'Accept-Encoding': 'gzip, deflate, br',
        'Cache-Control': 'no-cache',
        'Pragma': 'no-cache'
    }

    # Iterate through the combined keyword strings and search for jobs
    for keywords in keywords_list:
        # Remove the following line to prevent "searching" message
        # print(f"Searching for jobs with combined keywords: {keywords} in {location}")

        # Call the search_jobs function with the combined keyword query
        job_listings = search_jobs(query=keywords, location=location, page=page, num_pages=num_pages)

        # Check if job results exist
        if job_listings.get('data'):
            for job in job_listings['data']:
                experience_info = job.get('job_required_experience', {})
                required_experience_months = experience_info.get('required_experience_in_months', 'Not specified')
                experience_required = experience_info.get('experience_mentioned', 'Not specified')

                job_info = {
                    'title': job.get('job_title', 'N/A'),
                    'company': job.get('employer_name', 'N/A'),
                    'location': job.get('location', 'N/A'),
                    'posted_date': job.get('job_posted_at_datetime_utc', 'N/A'),
                    'apply_link': job.get('job_apply_link', 'N/A'),
                    'experience': f"{required_experience_months} months of experience required" if experience_required == "true" else "Experience not mentioned",
                    'skills_required': ', '.join(job.get('job_highlights', {}).get('Qualifications', ['Not specified'])),
                    'responsibilities': ', '.join(job.get('job_highlights', {}).get('Responsibilities', ['Not specified']))
                }

                # Display additional information if requested
                if extra_info:
                    for info in extra_info:
                        if info in job_info and job_info[info] != 'N/A':
                            print(f"{info.capitalize()}: {job_info[info]}")

                # Print the job details
                print(f"Job Title: {job_info['title']}")
                print(f"Company: {job_info['company']}")
                print(f"Location: {job_info['location']}")
                print(f"Posted Date: {job_info['posted_date']}")
                print(f"Apply Link: {job_info['apply_link']}")
                print(f"Skills Required: {job_info['skills_required']}")
                print(f"Responsibilities: {job_info['responsibilities']}")
                print(f"Experience: {job_info['experience']}\n")

        # Remove the "no results" message
        # else:
        #     print(f"No job results found for the combined query: {keywords}")

        # Introduce a random delay to mimic human browsing but suppress the message
        browse_delay = random.uniform(5, 15)
        time.sleep(browse_delay)  # Keep the delay but remove the printed message


# Example usage
if __name__ == "__main__":
    # Iterate through the list of combined keyword strings
    scrape_jobs(cybersecurity_keywords, location="USA", extra_info=["location"], page=1, num_pages=1)

The output, 1 of many:

Job Title: Penetration Tester
Company: Glocomms
Location: N/A
Posted Date: 2024-08-16T18:35:45.000Z
Apply Link: https://www.glocomms.com/job/penetration-tester-4?utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic
Skills Required: 3+ years of experience in application penetration testing and software engineering, preferably with enterprise software/systems, Proficiency in languages such as C#, Java, Ruby, Go, Python, etc, Proven ability to produce detailed penetration test reports tailored for both executives and developers, with clear prioritization and mitigation strategies, Strong experience with the OWASP testing guide and a deep understanding of industry-standard security practices, Familiarity with various web frameworks and technologies, including JavaScript, XML, SOAP, and JSON
Responsibilities: In this role, you will take ownership of evaluating the security of features and products, independently planning and executing penetration tests, and documenting your findings in accordance with industry best practices, As a key member of our team, you will advocate for and implement software security best practices, work closely with stakeholders to ensure that security is a fundamental part of the development process, and develop comprehensive threat models for proposed features, You will have the independence to plan and execute penetration tests, showcasing your expertise in vulnerability identification and resolution, You'll play a crucial role in promoting software security best practices, driving a culture of security awareness within the organization, Work alongside stakeholders to integrate security into the design and development of features, ensuring robust security measures are in place
Experience: 36 months of experience required


Adding the 24months(2year) parameter. ****# Filter jobs based on experience (less than or equal to 24 months)
                if required_experience_months <= 24:
                    experience_required = experience_info.get('experience_mentioned', 'Not specified')****

The code:

import http.client
import json
import time
import random
from fake_useragent import UserAgent

# New list with the provided combined keyword strings
cybersecurity_keywords = [
    "Network Security",
    "Penetration Testing",
    "Incident Response",
    "Threat Intelligence",
    "Vulnerability Assessment",
    "Malware Analysis",
    "Risk Management",
    "Security Operations",
    "Encryption",
    "Identity and Access Management",
    "Security Information and Event Management (SIEM)",
    "Firewall Management",
    "Cybersecurity Compliance",
    "Cloud Security",
    "Data Loss Prevention"
]

# Function to search for jobs using the JSearch API
def search_jobs(query, location, page=1, num_pages=1, date_posted='all'):
    # Set up the connection and request
    conn = http.client.HTTPSConnection("jsearch.p.rapidapi.com")

    # Replace these values with your own RapidAPI credentials
    headers = {
        'x-rapidapi-key': "072f716e1fmsh1d95c184aa5c087p18909cjsn7bb6a3435ed3",  # Enter your own RapidAPI key here
        'x-rapidapi-host': "jsearch.p.rapidapi.com"
    }

    # Construct the URL with query parameters
    request_url = f"/search?query={query.replace(' ', '%20')}&location={location}&page={page}&num_pages={num_pages}&date_posted={date_posted}"

    # Make the GET request
    conn.request("GET", request_url, headers=headers)

    # Get the response
    res = conn.getresponse()
    data = res.read()

    # Decode the response
    decoded_data = data.decode("utf-8")

    # Parse the JSON response
    job_results = json.loads(decoded_data)

    return job_results


# Function to scrape jobs using the combined keyword strings
def scrape_jobs(keywords_list, location="USA", extra_info=None, page=1, num_pages=1):
    # Rotate user-agents to avoid getting blocked
    ua = UserAgent()
    headers = {
        'User-Agent': ua.random,
        'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
        'Accept-Language': 'en-US,en;q=0.9',
        'Referer': location,
        'Connection': 'keep-alive',
        'Upgrade-Insecure-Requests': '1',
        'DNT': '1',  # Do Not Track request header
        'Accept-Encoding': 'gzip, deflate, br',
        'Cache-Control': 'no-cache',
        'Pragma': 'no-cache'
    }

    # Iterate through the combined keyword strings and search for jobs
    for keywords in keywords_list:
        # Call the search_jobs function with the combined keyword query
        job_listings = search_jobs(query=keywords, location=location, page=page, num_pages=num_pages)

        # Check if job results exist
        if job_listings.get('data'):
            for job in job_listings['data']:
                experience_info = job.get('job_required_experience', {})

                # Handle missing or None values
                required_experience_months = experience_info.get('required_experience_in_months', None)
                if required_experience_months is not None:
                    required_experience_months = int(required_experience_months)
                else:
                    required_experience_months = 0

                # Filter jobs based on experience (less than or equal to 24 months)
                if required_experience_months <= 24:
                    experience_required = experience_info.get('experience_mentioned', 'Not specified')

                    job_info = {
                        'title': job.get('job_title', 'N/A'),
                        'company': job.get('employer_name', 'N/A'),
                        'location': job.get('location', 'N/A'),
                        'posted_date': job.get('job_posted_at_datetime_utc', 'N/A'),
                        'apply_link': job.get('job_apply_link', 'N/A'),
                        'experience': f"{required_experience_months} Not Specified" if experience_required == "true" else "Experience not mentioned",
                        'skills_required': ', '.join(job.get('job_highlights', {}).get('Qualifications', ['Not specified'])),
                        'responsibilities': ', '.join(job.get('job_highlights', {}).get('Responsibilities', ['Not specified']))
                    }

                    # Display additional information if requested
                    if extra_info:
                        for info in extra_info:
                            if info in job_info and job_info[info] != 'N/A':
                                print(f"{info.capitalize()}: {job_info[info]}")

                    # Print the job details
                    print(f"Job Title: {job_info['title']}")
                    print(f"Company: {job_info['company']}")
                    print(f"Location: {job_info['location']}")
                    print(f"Posted Date: {job_info['posted_date']}")
                    print(f"Apply Link: {job_info['apply_link']}")
                    print(f"Skills Required: {job_info['skills_required']}")
                    print(f"Responsibilities: {job_info['responsibilities']}")
                    print(f"Experience: {job_info['experience']}\n")

        # Introduce a random delay to mimic human browsing but suppress the message
        browse_delay = random.uniform(5, 15)
        time.sleep(browse_delay)


# Example usage
if __name__ == "__main__":
    # Iterate through the list of combined keyword strings
    scrape_jobs(cybersecurity_keywords, location="USA", extra_info=["location"], page=1, num_pages=1)


The output:

Job Title: Penetration Tester - Clearance Required - Remote
Company: MindPoint Group
Location: N/A
Posted Date: 2024-09-06T11:39:41.000Z
Apply Link: https://www.linkedin.com/jobs/view/penetration-tester-clearance-required-remote-at-mindpoint-group-4018167450?utm_campaign=google_jobs_apply&utm_source=google_jobs_apply&utm_medium=organic
Skills Required: Minimum of 2 years of general work experience and 2 years of relevant experience in functional responsibility, Bachelor-s Degree, or an equivalent combination of formal education, and experience, Must have a strong technical background and understand system architecture and design, operating systems, network infrastructure, software installation on test platforms, software development, database, and operating systems, Security, Software Development, Networking, and/or Systems Administrator Experience, Deep understanding of 3-tiered Web Applications and Mobile Application Architectures, Manual Penetration Testing Experience (i.e. mapping applications, injecting SQLi, XSS, XXE, exploit creation), Must have Commercial Web Application Tool Experience (i.e, BurpSuite, AppScan, WebInspect), Network Penetration Testing Tool Experience (i.e, Exceptional communication skills, with the ability to explain the technical details of OWASP Top 10 and other vulnerabilities from C-levels to developers in a large professional environment, Web Services Security Penetration Testing Experience, Software Development and/or Scripting Experience in .NET, C++, Java, C#, perl, python, or bash, Mobile Application Penetration Testing (i.e, iOS, Android, Windows, Blackberry), Database Experience (DBA or security penetration testing), Source Code Review (aka Static Analysis) Experience, Excellent technical writing skills and attention to detail
Responsibilities: Conducts vulnerability assessments, Carries out penetration tests, performs social engineering tests, Analyzes technical security weaknesses, Performs risk analyses and develops exploits, Researches and maintains proficiency in tools, techniques, countermeasures, and trends in computer and network vulnerabilities, data hiding, and encryption
Experience: 24 Not Specified


Exportation To Csv & also adding the salary header:

The Code:

import http.client
import json
import time
import random
import csv
from fake_useragent import UserAgent

# New list with the provided combined keyword strings
cybersecurity_keywords = [
    "Network Security",
    "Penetration Testing",
    "Incident Response",
    "Threat Intelligence",
    "Vulnerability Assessment",
    "Malware Analysis",
    "Risk Management",
    "Security Operations",
    "Encryption",
    "Identity and Access Management",
    "Security Information and Event Management (SIEM)",
    "Firewall Management",
    "Cybersecurity Compliance",
    "Cloud Security",
    "Data Loss Prevention"
]

# Function to search for jobs using the JSearch API
def search_jobs(query, location, page=1, num_pages=1, date_posted='all'):
    # Set up the connection and request
    conn = http.client.HTTPSConnection("jsearch.p.rapidapi.com")

    # Replace these values with your own RapidAPI credentials
    headers = {
        'x-rapidapi-key': "5edb261a72msh00f84c33dba27a4p1d2680jsn6b062ef2fe86",  # Enter your own RapidAPI key here
        'x-rapidapi-host': "jsearch.p.rapidapi.com"
    }

    # Construct the URL with query parameters
    request_url = f"/search?query={query.replace(' ', '%20')}&location={location}&page={page}&num_pages={num_pages}&date_posted={date_posted}"

    # Make the GET request
    conn.request("GET", request_url, headers=headers)

    # Get the response
    res = conn.getresponse()
    data = res.read()

    # Decode the response
    decoded_data = data.decode("utf-8")

    # Parse the JSON response
    job_results = json.loads(decoded_data)

    return job_results

# Function to scrape jobs using the combined keyword strings and save results to a CSV file
def scrape_jobs_to_csv(keywords_list, location="USA", extra_info=None, page=1, num_pages=1, csv_filename="cybersecurity_jobs.csv"):
    # Rotate user-agents to avoid getting blocked
    ua = UserAgent()

    # Open CSV file for writing
    with open(csv_filename, mode='w', newline='', encoding='utf-8') as csv_file:
        fieldnames = ['Job Title', 'Company', 'Location', 'Posted Date', 'Apply Link', 'Skills Required', 'Responsibilities', 'Experience', 'Salary']
        writer = csv.DictWriter(csv_file, fieldnames=fieldnames)

        # Write the header
        writer.writeheader()

        # Iterate through the combined keyword strings and search for jobs
        for keywords in keywords_list:
            # Call the search_jobs function with the combined keyword query
            job_listings = search_jobs(query=keywords, location=location, page=page, num_pages=num_pages)

            # Check if job results exist
            if job_listings.get('data'):
                for job in job_listings['data']:
                    experience_info = job.get('job_required_experience', {})

                    # Handle missing or None values
                    required_experience_months = experience_info.get('required_experience_in_months', None)
                    if required_experience_months is not None:
                        required_experience_months = int(required_experience_months)
                    else:
                        required_experience_months = 0

                    # Extract salary information from the job listing
                    salary_min = job.get('job_min_salary', 'N/A')
                    salary_max = job.get('job_max_salary', 'N/A')
                    salary = f" {salary_min} - {salary_max}" if salary_min != 'N/A' and salary_max != 'N/A' else 'N/A'

                    # Filter jobs based on experience (less than or equal to 24 months)
                    if required_experience_months <= 24:
                        experience_required = experience_info.get('experience_mentioned', 'Not specified')

                        job_info = {
                            'Job Title': job.get('job_title', 'N/A'),
                            'Company': job.get('employer_name', 'N/A'),
                            'Location': job.get('location', 'N/A'),
                            'Posted Date': job.get('job_posted_at_datetime_utc', 'N/A'),
                            'Apply Link': job.get('job_apply_link', 'N/A'),
                            'Skills Required': ', '.join(job.get('job_highlights', {}).get('Qualifications', ['Not specified'])),
                            'Responsibilities': ', '.join(job.get('job_highlights', {}).get('Responsibilities', ['Not specified'])),
                            'Experience': f"{required_experience_months} Not Specified" if experience_required == "true" else "Experience not mentioned",
                            'Salary': salary
                        }

                        # Write the job info to the CSV file
                        writer.writerow(job_info)

            # Introduce a random delay to mimic human browsing but suppress the message
            browse_delay = random.uniform(5, 15)
            time.sleep(browse_delay)

    print(f"Job data has been saved to {csv_filename}")

# Example usage
if __name__ == "__main__":
    # Iterate through the list of combined keyword strings and export data to CSV
    scrape_jobs_to_csv(cybersecurity_keywords, extra_info=["location"], page=1, num_pages=1)


The Output Is stored In cybersecurity_jobs.csv

