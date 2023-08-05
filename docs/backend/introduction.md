---
sidebar_position: 1
---

# Introduction

As said in the previous pages, the backend is the reponsible for handling all the logic of our application.

### Tech stack

- Python
- PostgreSQL
- FastAPI 
- SQLAlchemy
- Celery (For processing the images and uploading it to S3)
- Redis (Rate limiter)

### Authentication

The authentication was implemented following a `Loging with Google` model for creating the account and log in, and `Twilio SMS` for validating the account.

### Image processing

Images are handled in a `Celery` task where they are processed by `opencv` and then stored in an `S3 Bucket` using `Boto3`.

This was handled this way so the user doesn't have to wait until the whole process is finished at the moment of creating a pet for their request to be fulfilled.