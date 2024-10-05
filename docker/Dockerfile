FROM supabase/postgres:latest

# Copy configuration files
COPY ./configs /etc/supabase

# Install necessary services
RUN apt-get update && apt-get install -y \
    postgrest \
    realtime \
    storage \
    auth \
    kong

# Expose ports
EXPOSE 5432 8000 3000 1337

# Start all services
CMD ["sh", "-c", "service postgresql start && \
                  postgrest /etc/supabase/postgrest.conf & \
                  realtime & \
                  storage & \
                  auth & \
                  kong start"]
