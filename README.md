# Final Secure Development Project in Django

##Setup

1. Install Python 3.9 or higher.
2. Install all requirements from requirements.txt.
3. Run with the function below:

##Run

```
python .\manage.py runserver_plus --cert .\openssl-ca\RootCA.crt
```

## Login attempts reset (if needed)
```
python manage.py axes_reset
```

## Admin Login

Username: ADMIN
Password: CSDjango1234

## Config
- Password length is determined IN `AUTH_PASSWORD_VALIDATORS -> UserAttributeSimilarityValidator -> OPTIONS -> min_length`
- Complex password is determined IN `AUTH_PASSWORD_VALIDATORS -> PasswordCharacterValidator -> OPTIONS`
- Password History (reuse password forbidden) IN `AUTH_PASSWORD_VALIDATORS -> UniquePasswordsValidator -> OPTIONS -> last_passwords`
- Password Forbidden list file path IN `AUTH_PASSWORD_VALIDATORS -> CommonPasswordValidator -> OPTIONS -> password_list_path`
  - Blacklisted password list should be in `commonPasswords.txt`.
- Logging in retries before block config IN `AXES_FAILURE_LIMIT` and blocking only by username (not ip) IN `AXES_ONLY_USER_FAILURES`
