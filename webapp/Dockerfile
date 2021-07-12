FROM python:3.9-slim
ENV PYTHONUNBUFFERED True
ENV APP_HOME /app
WORKDIR $APP_HOME
RUN pip install Flask gunicorn colorama numpy tensorflow nltk
COPY . ./ 
COPY ./tokenizers /home/nltk_data/tokenizers 
COPY ./corpora /home/nltk_data/corpora
CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 --timeout 0 main:app

