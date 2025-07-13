**Lead Generation Automation - AI-Powered Scraper for Targeted Outreach**

Python | Google Sheets | Serper API | Email Scraping

⚡ Ultimate automation for extracting targeted leads (email, channel, and content type) from long-form content creators across platforms like YouTube, Spotify, SoundCloud, and Apple Podcasts using search APIs and page scraping — powered by n8n workflows.

🧠 Overview
Lead Generation Automation is a smart and scalable workflow built using n8n that automates the discovery of long-form content creators and extracts verified email addresses, channel names, and content types. It integrates Google Sheets for organized storage and uses Serper’s Google Search API for precise lead targeting.

🔑 Key Features
🔍 Smart Lead Discovery  
- **Serper API Integration**: Executes Google search queries for long-form content from top platforms  
- **Massive Query Coverage**: Supports 80+ targeted queries for different content categories  
- **Content-Aware Filtering**: Focuses on podcasts, interviews, vlogs, lectures, and more

📩 Email Scraping Engine  
- **Deep Web Page Crawling**: Scrapes emails from metadata and visible page content  
- **Regex Filtering**: Detects valid, non-image email formats  
- **Smart Duplicate Remover**: Removes redundant emails automatically

🎥 Channel & Content Classification  
- **Auto Extraction**: Pulls channel name from `<title>` or `<h1>` tags  
- **Context Detection**: Categorizes content as "podcast", "vlog", "interview", etc. using content cues  
- **Data Clean-up**: Filters out irrelevant or low-quality entries

📊 Google Sheets Sync  
- **Live Export**: Saves data directly into connected Google Sheets  
- **Auto Update**: Appends or updates based on unique keys (email, channel, content type)  
- **Structured Columns**: Email, Channel Name, and Content Type

🔁 Workflow Automation  
- **n8n Compatible**: Visual, modular automation built in [n8n](https://n8n.io)  
- **Batch Support**: Processes results in chunks for scalability  
- **Multiple Lead Lists**: Routes leads to separate sheets (by category or quality)

🛠️ Setup Instructions
1. **Clone the Repository**  
```bash
git clone https://github.com/Samarcodesinpython/Lead-Generation-Automation
cd Lead-Generation-Automation
````

2. **Install & Run n8n**
   Install n8n globally:

```bash
npm install -g n8n
```

Start the n8n editor:

```bash
n8n
```

3. **Import Workflow**

* Upload the `Final_Boss_of_lead_Generation.json` file to n8n
* Set your **Serper API Key** in the relevant HTTP request nodes
* Link your **Google Sheets account** via OAuth credentials

4. **Configure Sheet IDs**

* Insert your target Google Sheet IDs in `Google Sheet` nodes (`documentId` and `sheetName`)
* Customize columns as per your lead storage format

🧪 Example Input Queries
These queries power the lead search process:

```text
site:youtube.com "hour long podcast"
site:spotify.com "business podcast"
site:soundcloud.com "full episode"
site:youtube.com "tech tutorial over 1 hour"
```

🧠 How It Works

1. Generates search queries across platforms
2. Fetches URLs from Serper API
3. Filters out irrelevant links
4. Requests and scrapes page data
5. Extracts email, channel, and content category
6. Saves clean leads to Google Sheets

🧾 Output Structure

| Email                                               | Channel Name   | Content Type |
| --------------------------------------------------- | -------------- | ------------ |
| [samarpodcast@xyz.com](mailto:samarpodcast@xyz.com) | Samar Talks AI | podcast      |
| [techguru@domain.com](mailto:techguru@domain.com)   | Tech Dive      | tutorial     |

🧱 Architecture

```
Lead-Generation-Automation/
├── Final_Boss_of_lead_Generation.json   # Core n8n workflow
├── README.md                            # This file
├── queries/                             # Sample queries (optional)
└── sheets/                              # Sample output Google Sheets (optional)
```

📈 Logging & Monitoring

* Google Sheets acts as a live audit trail
* Workflow includes error-tolerant nodes (e.g., continue on error for broken pages)

⚙️ Configuration Options

* `Max Batches`: Can tune for scaling
* `Filter Patterns`: Regex for filtering bad links/emails
* `Custom Queries`: Add more vertical-specific prompts

🧩 Integrations

* ✅ Serper API (Google Search)
* ✅ Google Sheets API
* ✅ Built on n8n (Visual Workflow Automation)

🧪 Debugging & Development

* Enable `continueOnFail` in page request nodes
* Use `Sticky Notes` in n8n for logic separation
* Validate using test queries like:

  ```text
  long+form+interview+site:youtube.com
  ```

💡 Future Improvements

* Add email validation score using APIs like ZeroBounce or NeverBounce
* Trigger Slack alerts on high-value leads
* Create UI dashboard with lead stats

🤝 Contributing
Contributions welcome! Here’s how:

```bash
git checkout -b feature/amazing-lead-finder
git commit -m "Add amazing logic"
git push origin feature/amazing-lead-finder
```

Then open a Pull Request 🙌

📄 License
This project is under the MIT License — see the `LICENSE` file for full details.

📬 Support

* Raise Issues via GitHub
* Reach out to the developer [@Samarcodesinpython](https://github.com/Samarcodesinpython)

🎯 Project Status: 🚧 Actively Developed
