# User autentication & profile management

[django-allauth](https://github.com/pennersr/django-allauth) is a mature and active project on Github which can let you quickly get relevant jobs done.

It already contains some useful features below

* User authentication
* Email authentication (with email confirmation)
* User registration, login, logout
* Simple user profile page
* Social login, signup

`Django-allauth` is not silver bullet so it might not help in some cases. So you might need to customize it or write code on your own to solve your problem.

## How to make it Restful

Please check [django-rest-auth](https://github.com/Tivix/django-rest-auth)

## How to override Django allauth

For example, you want to change the signup process of Django-allauth

You can create a custom CBV (class-based view) and declare it as subclass of Django-allauth signup view class.

```python
from allauth.account.views import SignupView

class CustomSignupView(SignupView):
    # Please overwrite method here
    pass


signup = CustomSignupView.as_view()
```

Then in your urls.py, 

```python
url(r"^accounts/signup/$", users.views.signup, name="account_signup"),
url(r'^accounts/', include('allauth.urls')),
```

## How to send the invitation

If you do not want to open your signup page and want your project invite-only. You can check links below

[django-invitations](https://github.com/bee-keeper/django-invitations)

[django-invitations & django-allauth](https://gist.github.com/nsomaru/53d0caf0981b56d57d77649b29c8cd1d)

