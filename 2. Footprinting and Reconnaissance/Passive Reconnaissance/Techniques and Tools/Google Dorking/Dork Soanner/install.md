<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/ee8b998d-db83-4086-af54-5edb4c6c0ed5" /># dorkScanner – Dork Scanner Scrapes Search Engines With Dorks

Getting the relevant results for our search is challenging work on google or on the internet. Being a Technical person we need to perform some advanced search through which we can get relevant results for our search. So this advanced searching process is known as Dorking. We fire up an advanced query that returns results that are only relevant to our query. Dork Scanner is an automated tool developed in the python language which is beneficial for searching things on the internet. We simply have to provide the query and the results are displayed on the terminal itself. Although Dork Scanner is a CLI-based tool and Google is said to be GUI based tool for the Dorking process. Dork Scanner is an open-source and free-to-use tool. Dork Scanner supports various search engines like Google, Bing, etc. Dork Scanner allows users to set the limit of results to be retrieved.

Note: Make Sure You have Python Installed on your System, as this is a python-based tool. Click to check the Installation process: Python Installation Steps on Linux

## Installation of Dork Scanner Tool on Kali Linux OS

Step 1: Check whether Python Environment is Established or not, use the following command.

```
pyothon3
```
<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/822e42d1-2535-413a-b603-da16e2df4c92" />

Step 2: Open up your Kali Linux terminal and move to Desktop using the following command.
```
cd Desktop
```
<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/2a2c8bfd-e7f9-4017-a3ed-b521a87fdec8" />

Step 3: You are on Desktop now create a new directory called Dork-Scanner using the following command. In this directory, we will complete the installation of the Dork-Scanner tool.

```
mkdir Dork-Scanner
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/1cb4e004-c33f-4216-92a8-21025db4028a" />

Step 4: Now switch to the Dork Scanner directory using the following command.

```
cd Dork-Scanner
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/c40876c0-8e4d-4bba-89c9-3a4d282b6ffd" />

Step 5: Now you have to install the tool. You have to clone the tool from GitHub.

```
git clone https://github.com/madhavmehndiratta/dorkScanner
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/0045da32-1687-4279-9d87-22b16939933e" />

Step 6: The tool has been downloaded successfully in the Dork-Scanner directory. Now list out the contents of the tool by using the below command.

```
ls
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/7de6ba1f-e135-4a6f-baff-21d592f11f15" />

Step 7: You can observe that there is a new directory created of the Dork Scanner tool that has been generated while we were installing the tool. Now move to that directory using the below command:

```
cd dorkScanner
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/002578dc-28e2-4504-b99e-49bde2f1fc65" />

Step 8: Once again to discover the contents of the tool, use the below command.

```
ls
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/11c61034-9e5d-4089-89f7-c8fa9ad0d0d5" />

Step 9: Download the required packages for running the tool, use the following command.

```
sudo pip3 install -r requirements.txt
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/182946d1-b0b1-4d92-9ecb-17614db91e2a" />

Step 10: Now we are done with our installation, Use the below command to view the help (gives a better understanding of the tool) index of the tool.

python3 dorkScanner.py --help

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/0ba2e769-6480-4f57-b838-8b5dc44dbd39" />

Working with Dork Scanner Tool on Kali Linux OS
Example 1: Query 1 = "inurl:wp-content/plugins/wp-jobsearch"

> python3 dorkScanner.py --query inurl:wp-content/plugins/wp-jobsearch --engine google --page 3 --process 3

1. In this example, We will be performing Dorking for Job Search Portal on the internet, We have passed the query of dork through --query tag and we are searching results on the google search engine.

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/b7f90968-eddd-4894-987b-05f7c74ce1ec" />

2. In the below Screenshot, We have got the results of our scan and this included only the job search-related results.

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/8a1feaa3-aeff-4e35-96b9-fd8115581586" />

Example 2: Query 2 =  "inurl:"index.php/user/password/""

> python3 dorkScanner.py --query inurl:"index.php/user/password/" --engine google --page 3 --process 3

1. In this Example, We are firing the query for detecting user and password files on the internet.

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/668ae6f1-3eb8-470e-892d-9f72576b79c5" />

2. In the below Screenshot, We have got the results that contain the path of index.php/user/password/.

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/6c80c853-9358-4eb3-ac5a-c13386e230b4" />

Example 3: Query 3 = "filetype:env "DB_PASSWORD""

> python3 dorkScanner.py --query "filetype:env "DB_PASSWORD"" --engine google --page 3 --process 3

1. In this example, We are searching for the .env files on the internet.

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/0d613a72-3f8b-4aad-8d1a-e755293bb2cb" />

2. In the below Screenshot, We have got the results that contain the .env files hosted on the server.

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/22bd67e5-9d69-414a-b4c3-9092938d9aea" />




