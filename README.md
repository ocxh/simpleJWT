# simpleJWT

- DRF
- simple JWT
- token

## Installation
```
pip install djangorestframework djangorestframework-simplejwt
```

## Project Configuration
### settings.py
```
INSTALLED_APPS = [
    ...
    'rest_framework_simplejwt',
    'rest_framework',
]
...
REST_FRAMEWORK = {
    ...
    'DEFAULT_AUTHENTICATION_CLASSES': (
        ...
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    )
    ...
}
```

### urls.py (Project Level)
```
from rest_framework_simplejwt.views import (
    TokenObtainPairView,
    TokenRefreshView,
)

urlpatterns = [
    ...
    path('sjwt/token/', TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('sjwt/token/refresh/', TokenRefreshView.as_view(), name='token_refresh'),
]
```
