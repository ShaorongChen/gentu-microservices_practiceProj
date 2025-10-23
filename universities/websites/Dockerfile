# Multi-stage build
FROM python:3.13-slim-bookworm AS builder

WORKDIR /python-docker

COPY requirements.txt requirements.txt
COPY UK_Universities.json UK_Universities.json

RUN pip3 install --upgrade pip
RUN pip3 install -r requirements.txt

COPY . .

FROM python:3.13-slim-bookworm

WORKDIR /python-docker

# Copy the installed packages from builder stage
COPY --from=builder /usr/local/lib/python3.13/site-packages /usr/local/lib/python3.13/site-packages

# Copy the application files
COPY . .

EXPOSE 5001
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]
