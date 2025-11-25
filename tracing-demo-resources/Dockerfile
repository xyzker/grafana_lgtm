FROM python:3.11-slim-bookworm
WORKDIR /trace
ENV FLASK_APP app.py
COPY requirements.txt .
RUN pip3 install -r requirements.txt
COPY app.py .
CMD ["flask", "run", "--host=0.0.0.0", "--port=8080"]
