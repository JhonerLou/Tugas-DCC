# Stage 1: Build stage
FROM gcc:latest AS builder

# Set working directory
WORKDIR /app

# Copy the C++ source file
COPY main.cpp .

# Compile the program
RUN g++ -static -O2 -o main main.cpp

# Stage 2: Runtime stage
FROM scratch

# Set working directory
WORKDIR /app

# Copy the compiled binary from builder
COPY --from=builder /app/main .

# Default command to run the program
CMD ["./main"]
