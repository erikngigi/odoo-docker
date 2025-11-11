# Use the official Odoo 18 image
FROM odoo:18.0

# Switch to root to install system-level packages
USER root

# Install Python dependencies (use --target for isolation)
RUN pip3 install --no-cache-dir --target=/opt/odoolibs \
    openpyxl \
    ofxparse \
    qifparse

# Add that directory to Python's module search path
ENV PYTHONPATH="/opt/odoolibs:$PYTHONPATH"

# Revert to Odoo user for security
USER odoo
