<h1>Splunk Log Analysis</h1>
<br>

<h2>Description</h2>

- This is a Take-home assignment from a prospective employer where they had SOC Analyst Candidates download Splunk (free), set it up, and Parse through 4 Log files (.csv) to find any <b>irregular activity</b>. Findings are presented in Powerpoint format. Assignment & Log files included! I would suggest Downloading the files first and trying it out on your own before viewing the Powerpoint (ChatGPT can help). <b>This is great practice for learning Splunk and practicing SPL Queries!</b>

- Log Analysis Instructions is the file describing the Assignent (.docx)
- The remaining 4 .csv files (comma-separated values) are the Log files for analysis. 
- The Powerpoint is my findings after parsing the Logs for unusual activity. Try doing the assignment yourself <b>BEFORE</b> viewing the Powerpoint solution. I promise you it is excellent experience for being a SOC Analyst.
<br>

<h2>Installing Splunk</h2>

1. Go to https://www.splunk.com/ and on the top right corner click the bar saying <b>Free Splunk</b> and create an Account.
 ![Splunkwebsite](https://github.com/user-attachments/assets/2156450e-0424-469b-bbfa-81b60743a52e)

2. Now that you are Logged in to your new Splunk Account, click <b>Free Splunk</b> again. On the Splunk Cloud Trials page click the Link for <b>Free Trials and Downloads page</b>.
   ![SplunkDL1](https://github.com/user-attachments/assets/e219d381-7537-4009-83df-4848af179662)

3. Then select the option for Splunk Enterprise.
   ![SplunkDL2](https://github.com/user-attachments/assets/5b244085-5f25-4bf6-a178-b58cabc94aaa)

4. Download the apropriate one for your O.S.
   ![SplunkDL3](https://github.com/user-attachments/assets/5bc8b55a-d19d-44e0-9951-4c2cc911e4c0)
<br>

<h2>Adding the .csv files</h2>

1. Now that you have Splunk installed, you access the Administrator Portal through your Browser http://127.0.0.1:8000/en-US/account/ and <b>Login</b>. You should Bookmark this page.
   ![SplunkLogin](https://github.com/user-attachments/assets/91400672-a15a-4950-a152-da276b6b52cf)

2. Click on the option to <b>Add Data</b>.
   ![SplunkAdddata](https://github.com/user-attachments/assets/07d6f3ec-09fc-4e27-8051-34b42bdf5b48)

3. <b>Upload</b> Files from my Computer option (e.g. CSV). Make sure on the <b>Set Source Type</b> step the file type is .csv, Splunk will automatically recognize this.
   ![SplunkUpload](https://github.com/user-attachments/assets/66188635-f184-45b2-8700-e5ee65ba38d7)

4. On the 3rd step: <b>Input Settings</b>, be sure to edit the <b>Host field value</b> to something unique. I chose "Novacoast" arbitrarily, but you can choose any name. The reason is so that you can later select all of the files by indicating the Host.
   ![SplunkUpload2](https://github.com/user-attachments/assets/f76431cc-1b8a-45ad-acd5-e14e37f53bc5)

5. Do this for each of the .csv files.
<br>

<h2>Navigating Splunk</h2>

- From your Home page in Splunk Enterprise, you will mainly be using the <b>Search & Reporting</b> App. This is the Splunk Search bar that allows you to search through (Parse) Logs via <b>Search Processing Language (SPL)</b>.
  ![SplunkSearchReporting](https://github.com/user-attachments/assets/09dec12f-e44a-4cbe-aa4d-01f90bd88e13)

- To see results from <b>all of the .csv log files</b> you just uploaded, type the SPL Query: <b><i>host="Novacoast" sourcetype="csv"</i></b>. Make sure to begin with your time range on the right of the search bar is set to <b>All Time</b>. *Note: the <i>Host=</i> field will be whatever Unique hostname you entered when uploading the .csv files to Splunk. So it will be <b><i>host="Unique Name" sourcetype="csv"</i></b>.
   ![Search1](https://github.com/user-attachments/assets/6334734e-b715-4712-a466-f8ada09da660)

- 98,733 results is alot! Too much for a human to inspect manually, but that's okay, that's what Splunk is for! On the left-hand Column,  you'll see <b>Selected Fields</b> and <b>Interesting Fields</b>. You can construct Queries to navigate the Data by these. Also you want to look at these to get a feel for the data or you can open the .csv files themselves in Excel (they are basically just really long spreadsheets).   
  ![SelectedFields](https://github.com/user-attachments/assets/110b8897-3b7e-4774-ac07-020aab0145f4)
  
- Here is an <b>Example Query</b> to get you started. Our goal is to look for Unusual Activity. Let's say we want to look for unsucessful Login attempts, We notice In the Interesting Fields column there is a <b>Message</b> field. So lets type in a Quiery that searches the Message field for messages that would indicate unsuccessful or failed login attempts:
   ![Search2](https://github.com/user-attachments/assets/b946d693-e512-4ee2-b9ec-4d9ad0f8390a)
  
- Remember, ChatGPT is your friend for constructing more complex queries to search through and narrow down the Data. If you find any unusual IP addresses that you suspect are malicious, check them on <a href="https://www.virustotal.com/gui/home/url" target="_blank">VirusTotal</a>. <b>Good Luck!</b>
