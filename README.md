# 📝 Stepwise.us - Django Blog Platform

A full-featured, modern blog platform built with Django, featuring user authentication, social login, and a beautiful responsive interface. Perfect for bloggers, content creators, and developers looking to understand Django's full-stack capabilities.

## 📖 Overview

Stepwise.us is a comprehensive blog application that demonstrates enterprise-level Django development patterns. Built with security, scalability, and user experience in mind, this platform provides everything needed to run a professional blogging site.

Whether you're a Django beginner looking to learn or an experienced developer seeking a solid foundation for your next project, Stepwise.us showcases best practices in web development.

## ✨ Features

### 🔐 User Management
- **Secure Registration & Authentication** - Email verification and password validation
- **Google OAuth Integration** - One-click sign-in with Google accounts via django-allauth
- **Profile Customization** - Personal profiles with avatar uploads and automatic image optimization
- **Password Recovery** - Email-based password reset flow
- **User Authorization** - Role-based access control for post management

### 📄 Blog Functionality
- **Full CRUD Operations** - Create, read, update, and delete blog posts
- **Smart Pagination** - Efficient content browsing with configurable page sizes
- **Author Pages** - Dedicated pages showing all posts from specific authors
- **Rich Post Details** - Individual post views with author information and timestamps
- **Post Ownership** - Users can only edit/delete their own content

### 🛡️ Security & UI
- **reCAPTCHA Protection** - Spam prevention on all forms
- **CSRF Tokens** - Built-in cross-site request forgery protection
- **Responsive Design** - Mobile-first Bootstrap 4 implementation
- **Media Management** - Automatic image resizing and optimization
- **SQL Injection Prevention** - Django ORM security features

## 🏗️ Architecture

```
┌─────────────────┐
│   Web Browser   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Django Views   │
│  - Blog Posts   │
│  - User Auth    │
└────────┬────────┘
         │
    ┌────┴────┐
    ▼         ▼
┌─────────┐ ┌──────────┐
│  Blog   │ │   User   │
│  App    │ │   App    │
└────┬────┘ └────┬─────┘
     │           │
     └─────┬─────┘
           ▼
    ┌──────────────┐
    │   Database   │
    │   (SQLite)   │
    └──────────────┘
```

## 🛠️ Technology Stack

| Component | Technology |
|-----------|------------|
| **Framework** | Django 4.1.3 |
| **Database** | SQLite (Dev), PostgreSQL (Production) |
| **Frontend** | Bootstrap 4, HTML5, CSS3 |
| **Authentication** | Django Allauth |
| **Forms** | Django Crispy Forms |
| **Image Processing** | Pillow |
| **Security** | django-recaptcha |
| **API Integration** | Google OAuth 2.0 |

## 🚀 Getting Started

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- Virtual environment (recommended)
- Google Account (for OAuth integration)

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/KhonS7/Stepwise.us.git
cd Stepwise.us
```

**2. Create and activate virtual environment**
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

**4. Set up environment variables**

Create a `.env` file in the project root (see `.env.example` for template):
```env
SECRET_KEY=your-secret-key-here
DEBUG=True
EMAIL_HOST_USER=your-email@gmail.com
EMAIL_HOST_PASSWORD=your-app-password
RECAPTCHA_SITE_KEY=your-recaptcha-site-key
RECAPTCHA_SECRET_KEY=your-recaptcha-secret-key
```

⚠️ **Security Note:** Never commit your `.env` file to version control!

**5. Run migrations**
```bash
python manage.py makemigrations
python manage.py migrate
```

**6. Create superuser**
```bash
python manage.py createsuperuser
```

**7. Run the development server**
```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000` in your browser 🎉

## 💡 Usage

### Creating Your First Post

1. Register an account at `/register`
2. Verify your email (if configured)
3. Navigate to "New Post" in the navbar
4. Write your content with title and body
5. Click "Post" to publish!

### Managing Your Profile

```
# Access your profile
Visit: http://127.0.0.1:8000/profile

# Update profile picture
- Click "Choose File"
- Select image
- Click "Update"

# View your posts
Click on your username → See all your published posts
```

## 📦 Project Structure

```
Stepwise.us/
│
├── 📁 blog/                    # Blog application
│   ├── migrations/            # Database migrations
│   ├── static/                # CSS, JavaScript, Images
│   │   └── blog/
│   │       └── main.css       # Custom styles
│   ├── templates/             # HTML templates
│   │   └── blog/
│   │       ├── home.html      # Homepage
│   │       ├── post_detail.html
│   │       └── post_form.html
│   ├── models.py              # Post model
│   ├── views.py               # View logic (CBVs)
│   └── urls.py                # URL routing
│
├── 📁 user/                    # User management app
│   ├── migrations/            # Database migrations
│   ├── templates/             # User templates
│   │   └── users/
│   │       ├── login.html
│   │       ├── register.html
│   │       └── profile.html
│   ├── models.py              # Profile model
│   ├── views.py               # User views
│   ├── forms.py               # Custom user forms
│   └── signals.py             # Auto-create profiles
│
├── 📁 django_project/          # Project configuration
│   ├── settings.py            # Main settings
│   ├── urls.py                # Root URL config
│   └── wsgi.py                # WSGI entry point
│
├── 📁 media/                   # User uploads
│   ├── default.jpg            # Default avatar
│   └── profile_pics/          # User avatars
│
├── 📄 .env.example             # Environment variables template
├── 📄 .gitignore               # Git ignore rules
├── 📄 db.sqlite3               # SQLite database
├── 📄 manage.py                # Django CLI
├── 📄 requirements.txt         # Python dependencies
└── 📄 README.md                # You are here!
```

## 🎯 Key Technical Achievements

✅ **Class-Based Views (CBVs)** - Leveraged Django's powerful CBVs for clean, reusable code  
✅ **User Authentication System** - Complete auth flow with registration, login, and password reset  
✅ **Social OAuth Integration** - Seamless Google Sign-In implementation  
✅ **Database Relationships** - Proper ForeignKey relationships between Users and Posts  
✅ **Form Validation** - Server-side validation with Crispy Forms styling  
✅ **Media Handling** - Automatic image processing and storage management  
✅ **Responsive Design** - Mobile-friendly interface with Bootstrap 4  
✅ **Security Best Practices** - CSRF protection, password hashing, and secure credential management  

## 🔧 Configuration

### 🔑 Google OAuth Setup

1. Visit [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project
3. Enable **Google+ API**
4. Create **OAuth 2.0 credentials**
5. Add authorized redirect URIs:
   ```
   http://127.0.0.1:8000/accounts/google/login/callback/
   ```
6. Add your Client ID and Secret to `.env`

### 📧 Email Configuration

For password reset functionality:

1. **Gmail Setup:**
   - Enable 2-Factor Authentication
   - Generate an App Password at [Google Account Security](https://myaccount.google.com/security)
   - Add credentials to `.env`

2. **Alternative SMTP:**
   - Use SendGrid, Mailgun, or AWS SES
   - Update `EMAIL_HOST` in settings and add credentials to `.env`

### 🔒 reCAPTCHA Setup

1. Register at [Google reCAPTCHA](https://www.google.com/recaptcha/admin)
2. Choose **reCAPTCHA v2** (Checkbox)
3. Add domains:
   - `127.0.0.1` (development)
   - Your production domain
4. Add Site Key and Secret Key to `.env`

## 📚 What You'll Learn

✅ Django project structure and app architecture  
✅ User authentication and authorization patterns  
✅ Database modeling with Django ORM  
✅ Class-Based Views (ListView, DetailView, CreateView, UpdateView, DeleteView)  
✅ Form handling and validation with Django Forms  
✅ Template inheritance and context processors  
✅ Static files and media management  
✅ Third-party package integration  
✅ Security best practices in web development  
✅ Environment-based configuration management  

## 🛡️ Security

This project implements several security best practices:

- Environment variables for sensitive data
- CSRF protection on all forms
- SQL injection prevention via Django ORM
- Password hashing with PBKDF2
- reCAPTCHA for spam prevention
- Secure session management
- XSS protection through template escaping

⚠️ **Before deploying to production:**
- Set `DEBUG = False`
- Update `ALLOWED_HOSTS`
- Use PostgreSQL or MySQL instead of SQLite
- Enable HTTPS
- Set secure cookie flags
- Configure proper static file serving

## 🚀 Deployment

### Recommended Platforms

- **Heroku** - Easy deployment with PostgreSQL add-on
- **PythonAnywhere** - Beginner-friendly Django hosting
- **DigitalOcean App Platform** - One-click deployment
- **AWS EC2** - Full control with Nginx + Gunicorn

### Quick Deploy to Heroku

```bash
# Install Heroku CLI
heroku login
heroku create stepwise-blog
heroku addons:create heroku-postgresql:mini
git push heroku main
heroku run python manage.py migrate
heroku run python manage.py createsuperuser
```

## 📊 Database

**Development:** SQLite (included)

**Production:** PostgreSQL (recommended)

Update `DATABASES` in `settings.py` for production:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'your_db_name',
        'USER': 'your_db_user',
        'PASSWORD': 'your_db_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

## 🎯 Future Enhancements

- [ ] **Rich Text Editor** - Integrate TinyMCE or CKEditor for better content creation
- [ ] **Comment System** - Add threaded comments on blog posts
- [ ] **Categories & Tags** - Organize posts with taxonomy
- [ ] **Search Functionality** - Full-text search across posts
- [ ] **Email Notifications** - Notify users of new posts from followed authors
- [ ] **Draft Posts** - Save posts as drafts before publishing
- [ ] **Social Sharing** - Share buttons for Twitter, Facebook, LinkedIn
- [ ] **Follow System** - Users can follow their favorite authors
- [ ] **Markdown Support** - Write posts in Markdown format
- [ ] **REST API** - Build API with Django REST Framework
- [ ] **Testing Suite** - Comprehensive unit and integration tests
- [ ] **Docker Support** - Containerized deployment
- [ ] **Redis Caching** - Cache posts for better performance

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Guidelines
- Follow PEP 8 style guide
- Write descriptive commit messages
- Add tests for new features
- Update documentation as needed

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Khon S.**

- GitHub: [@KhonS7](https://github.com/KhonS7)
- LinkedIn: [Khon S.](https://linkedin.com/in/khon-s)
- Email: js14841@nyu.edu

## 🙏 Acknowledgments

- **Django Software Foundation** - For the incredible framework
- **Bootstrap Team** - For the responsive CSS framework
- **django-allauth** - For seamless OAuth integration
- **django-crispy-forms** - For beautiful form rendering
- **Pillow** - For image processing capabilities
- **All Contributors** - Thank you for your support!

## 📞 Support

Need help? Have questions?

- 📧 **Email:** js14841@nyu.edu
- 💬 **Issues:** [GitHub Issues](https://github.com/KhonS7/Stepwise.us/issues)
- 📖 **Django Docs:** [docs.djangoproject.com](https://docs.djangoproject.com/)

---

⭐ **If you find this project helpful, please give it a star!**

💙 **Happy Coding!**

---

⚡ **Interested in my work? Check out my other projects:**
- [AI Code Agent](https://github.com/KhonS7/ai-code-agent) - LLM-powered autonomous coding assistant

**Built with ❤️ using Django**
