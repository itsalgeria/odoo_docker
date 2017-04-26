FROM camptocamp/odoo-project:10.0-2.0.0
MAINTAINER Camptocamp

# Project's specifics packages
RUN set -x; \
        apt-get update \
        && apt-get install -y --no-install-recommends \
        python-shapely \
        && apt-get clean \
        && rm -rf /var/lib/apt/lists/*

COPY ./requirements.txt ./
RUN pip install -r requirements.txt

ENV ADDONS_PATH="/opt/odoo/src/addons, \
  /opt/odoo/external-src/geospatial" \
  LIMIT_TIME_CPU=86400 \
  LIMIT_TIME_REAL=86400 \
  LIMIT_MEMORY_SOFT=1342177280 \
