FROM python:3.11-bullseye

# Install GEOS library
RUN apt-get update && apt-get install -y libgeos-dev

WORKDIR /code

COPY ./requirements.txt /code/requirements.txt

RUN pip install --no-cache-dir --upgrade -r /code/requirements.txt --timeout 100

#You may need to run `chmod +x ./backend/scripts/start.sh` on your host machine if you get a permission error
COPY ./scripts/start.sh /code/scripts/start.sh
RUN chmod +x /code/scripts/start.sh

COPY . /code/

ENTRYPOINT ["/code/scripts/start.sh"]
