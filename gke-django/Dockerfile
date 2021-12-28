FROM python:3.8.10

ENV PYTHONUNBUFFERED=1

# project directory
WORKDIR /app

# update pip
RUN pip install --upgrade pip

# copy everything to project directory 
COPY . /app

# install dependencies
RUN pip install -r requirements.txt
RUN python manage.py collectstatic --noinput                                         

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "core.wsgi:application"]
