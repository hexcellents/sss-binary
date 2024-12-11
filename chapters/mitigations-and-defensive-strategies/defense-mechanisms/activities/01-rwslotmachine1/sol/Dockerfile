# Stage 1: Build Stage
FROM gcc:latest AS build

WORKDIR /app

COPY rwslotmachine1.c .

# Compile the C code into an executable
RUN gcc -Wall -Wextra -O2 -o rwslotmachine1 rwslotmachine1.c

# Stage 2: Runtime Stage
FROM ubuntu:latest

WORKDIR /app

COPY --from=build /app/rwslotmachine1 /app/rwslotmachine1

EXPOSE 31344

# Run the application
CMD ["./rwslotmachine1"]
