# Chapter10

AWS 사이트
---
https://aws.amazon.com/ko/

rds, s3 환경 변수
---
~~~
set DJANGO_SETTINGS_MODULE=hello3.settings.prod_aws_eb
set DB_HOST=
set DB_USER=
set DB_PASSWORD=
set DB_NAME=
set DB_PORT=
set AWS_ACCESS_KEY_ID=
set AWS_SECRET_ACCESS_KEY=
set AWS_STORAGE_BUCKET_NAME=
set AWS_S3_REGION_NAME=ap-northeast-2
~~~

로컬서버에서 AWS RDS, S3 사용
---
~~~
python manage.py showmigrations --settings=hello3.settings.prod_aws_eb
python manage.py migrate --settings=hello3.settings.prod_aws_eb
python manage.py createsuperuser --settings=hello3.settings.prod_aws_eb
python manage.py collectstatic --settings=hello3.settings.prod_aws_eb
python manage.py runserver --settings=hello3.settings.prod_aws_eb
~~~

hello3/.ebextensions/options.config
---
~~~python
packages:
  yum:
    freetype-devel: []
    libjpeg-turbo-devel: []
    libpng-devel: []

option_settings:
  aws:elasticbeanstalk:container:python:
    WSGIPath: hello3/wsgi.py
~~~


