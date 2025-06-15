# CHROME-EXTENSION-FOR-TIME-TRACKING-AND-PRODUCTIVITY-ANALYTICS

COMPANY : CODTECH IT SOLUTIONS

NAME : DIVYA SHREE B

INTERN ID : COD08111

DOMAIN : FULL STACK WEB DEVELOPMENT

DURATION : 4 WEEKS

MENTOR : NEELA SANTOSH

DESCRIPTION : Chrome extension for time tracking and productivity analytics

Developing a Chrome extension for tracking time and analyzing productivity begins with leveraging Chrome’s Manifest v3 framework to establish a background process that monitors tab behavior. This background script detects when users shift focus between tabs, using the chrome.tabs.onActivated and chrome.tabs.onUpdated events. Each time focus changes, the script calculates the duration spent on the previous domain and persists this data in local storage via chrome.storage.local. This approach ensures the extension remains lightweight and responsive to minimize impact on browser performance, a critical consideration given studies on extension overhead 

To maintain user privacy and security, the extension is designed to keep all browsing data local by default. Optionally, users can enable synchronization, which periodically transmits aggregated time data to a remote backend. A simple heuristic or user-configured list categorizes domains as productive (such as development tools) or unproductive (such as social media), labeling each record before saving. For greater flexibility, the backend could support AI-based enhancements to classify unfamiliar domains. This lets the system learn over time and provide refined analytics.

The backend infrastructure is built using Node.js and Express, paired with MongoDB and Mongoose. When sync runs, it sends batches of {domain, duration, date, category} entries to the /track endpoint. These entries are persisted, and users can view analytics via a /weekly endpoint that aggregates recent data by domain and category. Aggregation pipelines calculate total time per domain and categorize it, enabling insights into time distribution. This model aligns with open-source samples that store time entries and generate visual reports .

Visualization is handled in a React-based dashboard, which retrieves aggregated data via Axios and renders it using charting libraries such as Recharts or Chart.js. Users see bar graphs showing top domains by time, line charts for trends across the week, and pie charts breaking down productive against unproductive time. Export features allow users to download CSV reports for offline analysis. Analysis tools reveal patterns like excessive time spent on distractions, empowering users to adjust habits.

Marketplace alternatives such as Activity Time Tracker emphasize similar functionality: auto-categorized visuals, real-time charts, local-first design, and privacy 
chromewebstore.google.com
. They also reveal demand for such tools—users appreciate intuitive interfaces that reveal browsing habits. Professional solutions like Clockify and Toggl Track extend this model by offering integrations, idle detection, reminders, project tracking, and Pomodoro timers 

The extension’s background process is deliberately minimal—tracking only domain and duration without invading user confidentiality. This balances data richness with performance, as extensions can negatively affect browser speed if poorly designed 

The technical build begins with manifest settings that include permissions for active tab tracking and local storage. The background script manages focus events, duration intervals, and periodic sync. The optional popup serves immediate user feedback, displaying current session details. On the backend, a robust API accepts time logs and serves aggregated results. React components present time usage visually through charts and tables. This cohesive flow ensures seamless data collection, storage, and presentation.

Overall, this time-tracking solution empowers individuals to understand and optimize their online behavior. By distinguishing productive from unproductive activities, visualizing habits, and optionally exporting data, users can reshape their digital routines. Future enhancements might include customizable categorization, AI-driven domain classification, or integration with task systems like Asana or Jira 

It could also support user accounts with authentication and server-side per-user storage for cross-device consistency.

OUTPUT : 

![Image](https://github.com/user-attachments/assets/70687cec-9182-4c29-8cd3-8ff8ac1670d8)
