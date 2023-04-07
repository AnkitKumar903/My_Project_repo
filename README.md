# My_Project_repo 
#lepton_assignment

#For_finding_the_name_of_the_store
from bs4 import BeautifulSoup  
import requests  
  
url="http://www.spencersretail.com/stores/spencers-neighborhood-store-sec-14gurgaon/"  
  
# Make a GET request to fetch the raw HTML content  
html_content = requests.get(url).text  
  
# Parse the html content  
soup = BeautifulSoup(html_content, "html5lib")  
print(soup.title.text)  # print the parsed data of html  

r=requests.get("http://www.spencersretail.com/stores/spencers-neighborhood-store-sec-14gurgaon/")
soup=BeautifulSoup(r.content,"html.parser")
div_text=soup.find("article",{"class":"node node-spencer-stores view-mode-full"}).get_text()

#We find the type of data which stored in div_text
type(div_text)

#Find indexing no.

s1=div_text.index("Spencer's")

print(s1)

#Find address by slicing method

s2=div_text[5:125]
print(s2)

#Find Phone no. by slicing method
p1=div_text[126:147]
print(p1)

#Find timing by slicing method
t1=div_text[148:254]
print(t1)

import requests
r=requests.get("https://proxyway.com/")
soup=BeautifulSoup(r.content,"html.parser")
d_text=soup.find("div",{"class":"row"}).get_text()
print(d_text)

l1=d_text.index('Reviews')
print(l1)

#for_location_of_the_shop
l2=d_text[210:245]
print(l2)
