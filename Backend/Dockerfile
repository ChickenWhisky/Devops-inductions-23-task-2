# Use the official Rust image as the base image
FROM rust:1.70

# Install system dependencies required for Diesel and PostgreSQL
RUN apt update && apt upgrade -y && apt install libpq-dev

# Copy the Cargo.toml and Cargo.lock files to the container
COPY . .

RUN cargo install diesel_cli --no-default-features --features postgres
RUN chmod +x ./initialize_backend.sh

CMD [ "./initialize_backend.sh" ]
