FROM python:3.12-slim

RUN pip install uv

WORKDIR /app

COPY requirements.txt .

RUN uv venv && \
    /bin/bash -c 'source /app/.venv/bin/activate' && \
    uv pip install --system -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["uv", "run", "fastapi", "run", "main.py"]