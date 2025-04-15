
# 🚀 Pump Quoting Automation System

A full-stack, production-ready web application built for a pump manufacturing company to generate professional customer quotes.  
The frontend is hosted via WordPress (GoDaddy cPanel), which connects to a live Flask API hosted on Heroku, backed by a secure MySQL database.

> 📌 This is a **public showcase version** of a private production repository. The original includes proprietary data and secret configs.

---

## 📽️ Demo

[![Watch the demo](https://img.youtube.com/vi/JDMOYXBoGl0/0.jpg)](https://youtu.be/JDMOYXBoGl0)

---

## 🌐 Deployment

This project is actively running in production:

- **Frontend:** Static HTML/JS/CSS deployed via GoDaddy’s WordPress cPanel
- **Backend API:** Python Flask API deployed on Heroku
- **Database:** Secure remote MySQL database
- **Communication:** JavaScript (frontend) makes real-time API calls to Heroku backend

> This system is actively used to generate real customer quotes.

---

## 🧩 Features

- 🖥️ **Frontend:** Responsive web form using HTML, CSS, and vanilla JavaScript  
- 🔌 **Backend:** Python Flask API to process inputs and generate pump recommendations  
- 🗄️ **Database:** MySQL storing pump models, specs, and pricing data  
- 🧮 **Advanced Logic:**
  - Unit conversions (GPH ↔ LPH, PSI ↔ Bar)
  - Optional accessories with "Call for Pricing" (C/F) logic
  - Automatic model selection and final price calculation
- 📝 **PDF Generation:** Branded quotes with customer details and accessory breakdown
- 📧 **Email Automation:** Sends PDF quotes to customer emails automatically
- ⚙️ **Scalable:** Easily update models, pricing, and accessories as the business evolves

---

## 🛠️ Tech Stack

| Category        | Technologies                               |
|----------------|--------------------------------------------|
| Frontend       | HTML, CSS, JavaScript                      |
| Backend        | Python, Flask                              |
| Database       | MySQL                                      |
| PDF Generator  | ReportLab                                  |
| Email Service  | SMTP                                       |
| Hosting        | Heroku (API), GoDaddy WordPress (Frontend) |
| API Testing    | Postman, Console Debugging                 |

---

## 📁 Project Structure

```
├── main.py                 # Flask API backend (logic, PDF, email)
├── page.html               # HTML frontend form
├── call_api.js             # JS form handling + API calls
├── custom-pump-tool.css    # CSS styling for layout
├── logo.png                # Logo used in PDF generation
├── api-proxy.php           # (Optional) Proxy for server environments
├── requirements.txt        # Python dependencies
├── setup_pump_database.sql # Sample SQL schema for demo purposes
└── README.md               # Project documentation
```

---

## ⚙️ Installation & Setup

### 1. Clone the repo
```bash
git clone https://github.com/Savant-sys/your-repo.git
cd your-repo
```

### 2. MySQL setup
- Create a database named `local_pump_info`
- Run [`setup_pump_database.sql`](setup_pump_database.sql) to create the database and `pumps` table  
  *(Includes a sample structure only — no sensitive data)*

Update `main.py` with your MySQL credentials:
```python
db_config = {
    "host": "localhost",
    "user": "root",
    "password": "YOUR_MYSQL_PASSWORD",
    "database": "local_pump_info"
}
```

### 3. (Optional) Create virtual environment
```bash
python -m venv venv
venv\Scripts\activate      # Windows
# or
source venv/bin/activate   # macOS/Linux
```

### 4. Install dependencies
```bash
pip install -r requirements.txt
```

### 5. Email config (optional)
Update this section in `main.py` if using email:
```python
SMTP_SERVER = 'smtp.bizmail.yahoo.com'
SMTP_PORT = 465
EMAIL_ADDRESS = 'your_email@example.com'
EMAIL_PASSWORD = 'your_email_password'
```

> ⚠️ Skip this step if you only want to download the PDF locally.

### 6. Run backend (Flask API)
```bash
py main.py
```

Visit: `http://localhost:5000`

### 7. Run frontend (form)
```bash
python -m http.server 8000
```

Open: `http://localhost:8000/page.html`

---

## 🧪 How to Use

1. Open the form in your browser  
2. Enter customer info and pump specs  
3. Click **Find Pump**  
4. Click **Get Quote PDF** to download or email the quote  

---

## 🧯 Troubleshooting

- **CORS issues:** Install `flask-cors`
- **MySQL errors:** Check your credentials and DB name
- **PDF not working:** Ensure `reportlab` is installed
- **Email not sending:** Double-check SMTP settings and credentials

---

## 🔮 Future Improvements

- 📊 Admin dashboard for pump management
- 📂 Quote history tracking
- 🔐 API authentication
- 🖼️ UI design improvements
- 📁 Drag-and-drop CSV import for pump models

---

## 👨‍💻 Author

**Michael Khuri**

- 🌐 [michaelkhuri.com](https://michaelkhuri.com)
- 💼 [LinkedIn](https://linkedin.com/in/michael-khuri)
- 🧩 [GitHub](https://github.com/Savant-sys)

---

## 🙌 Acknowledgments

- Created during my internship to streamline quoting workflows at AcuFlow company.
- This version excludes sensitive data and is intended for public portfolio purposes only.
