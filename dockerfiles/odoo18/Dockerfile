# Use the official Odoo 18 image
FROM odoo:18.0

# Switch to root to install system-level packages
USER root

# Install fonts
RUN apt-get update && apt-get install -y xfonts-base xfonts-75dpi

# Install Python dependencies (use --target for isolation)
RUN pip3 install --no-cache-dir --target=/opt/odoolibs \
    openpyxl \
    ofxparse \
    qifparse

# Add that directory to Python's module search path
ENV PYTHONPATH=/usr/lib/python3/dist-packages:/custom-addons

# Revert to Odoo user for security
USER odoo
