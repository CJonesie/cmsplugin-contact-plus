
## Installation

1. To clone the latest commit from GitHub,
  '''
	git clone https://github.com/CJonesie/cmsplugin-contact-plus.git
	'''
  
  Once its cloned find the requirements.txt of the plugin and run
  '''
  pip install -r requirements.txt
  '''

2. cmsplugin-contact-plus requires https://github.com/iambrandontaylor/django-admin-sortable as dependency. 
It gets installed with the requirements.txt but please have a look at the "Supported Django Versions", "Installation", and "Configuration" sections of the [README](https://github.com/iambrandontaylor/django-admin-sortable/blob/master/README.md).

3. Put ''cmsplugin_contact_plus'' and ''adminsortable'' in your INSTALLED_APPS 'settings.py' section and verify that the [ADMINS](https://docs.djangoproject.com/en/dev/ref/settings/#admins) setting is set as well.

4. Don't forget to migrate your database.
5. Configure Django's [e-mail settings](https://docs.djangoproject.com/en/1.8/topics/email/#quick-example) appropriately.

## development Email set up

1. if you want it to send to the console set
  '''
  EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'
  '''
  in the settings
  or 
  '''
  EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
  '''
  if you want to set up a smtp server like mailhog

## ReCaptcha set up

1. As long as you ran
  ''' 
   pip install -r requirements.txt
  '''
  for the project than recaptca2 is installed and all that you need is to set it up following these steps
  
2. To make the reCAPTCHA field type available to your users, add 'snowpenguin.django.recaptcha2' to your 'INSTALLED_APPS'
    and define your 'RECAPTCHA_PUBLIC_KEY' and 'RECAPTCHA_PRIVATE_KEY' as described in [django-recaptcha's README]
   (https://github.com/praekelt/django-recaptcha/blob/develop/README.rst). A single reCAPTCHA instance per page is supported.
   
(4.) Default Keys for development
RECAPTCHA_PUBLIC_KEY = '6LeIxAcTAAAAAJcZVRqyHh71UMIEGNQ_MXjiZKhI'
RECAPTCHA_PRIVATE_KEY = '6LeIxAcTAAAAAGG-vFI1TnRWxMZNFuojJ4WifJWe'

(5.) If you require a proxy, add a RECAPTCHA_PROXY setting, for example:

RECAPTCHA_PROXY = 'http://127.0.0.1:8000'
