FROM cirrusci/flutter:stable

# Install any additional dependencies you need.
RUN apt-get update && apt-get install -y \
    libglu1-mesa \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory
WORKDIR /workspace

# Start the Flutter daemon
CMD ["flutter", "daemon"]
