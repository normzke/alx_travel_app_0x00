# ALX Travel App

A Django-based travel application that allows users to browse and book travel listings.

## Features

- Browse travel listings
- Book accommodations
- Leave reviews
- User authentication
- Admin dashboard

## Project Structure

```
alx_travel_app/
├── alx_travel_app/          # Main project directory
│   ├── settings.py         # Project settings
│   ├── urls.py            # Main URL configuration
│   └── wsgi.py           # WSGI configuration
├── listings/              # Listings app
│   ├── models.py         # Database models
│   ├── serializers.py    # API serializers
│   ├── views.py          # View logic
│   └── urls.py           # App URL configuration
├── manage.py             # Django management script
└── requirements.txt      # Project dependencies
```

## Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/normzke/alx_travel_app_0x00.git
cd alx_travel_app
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Set up environment variables:
Create a `.env` file in the project root with:
```
SECRET_KEY=your-secret-key-here
```

5. Run migrations:
```bash
python manage.py makemigrations
python manage.py migrate
```

6. Create a superuser:
```bash
python manage.py createsuperuser
```

7. Run the development server:
```bash
python manage.py runserver
```

## API Endpoints

- `/api/listings/` - List and create travel listings
- `/api/bookings/` - Manage bookings
- `/api/reviews/` - Handle user reviews

## Database Models

### Listing
- title: CharField
- description: TextField
- price: DecimalField
- location: CharField
- created_at: DateTimeField
- updated_at: DateTimeField

### Booking
- listing: ForeignKey to Listing
- user: ForeignKey to User
- check_in: DateField
- check_out: DateField
- status: CharField (choices: pending, confirmed, cancelled)
- created_at: DateTimeField

### Review
- listing: ForeignKey to Listing
- user: ForeignKey to User
- rating: IntegerField
- comment: TextField
- created_at: DateTimeField

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License.
