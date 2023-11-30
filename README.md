# whatsapp-bot

## Requirements

- Python 3.10.12
- Python3 pip ( sudo apt install -y python3-pip )

## 1. Setup

### 1.1 Creating Flask virtualenv

(only needed first time)

```sh
  $ python3 -m venv venv
```

### 1.2 Activating Flask virtualenv

```sh
  $ source venv/bin/activate
```

From now on, you shall see **(venv)** written on the left side of command prompt, indicating that you're inside of the virtualenv

### 1.3 Installing requirements inside Flask virtualenv

(only needed first time)

```sh
  $ poetry install
```

### 1.4 Configure needed environment variables inside .env file

(only needed first time. Examples available in **.env.production-example** and **.env.development-example**)

```sh
  $ cp .env.X-example .env
```

## 2. Run

(needs to be executed inside Flask virtualenv. See 1.2)

```sh
  $ python3 main.py
```

## Off: to setup production process (PM2 process at EC2)

(needs to be executed inside Flask virtualenv and to have Gunicorn installed)

```sh
  $ pm2 start --name NAME_HERE "gunicorn wsgi:app --workers 3 -b localhost:3399"
```
