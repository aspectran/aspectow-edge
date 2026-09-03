# Aspectow Edge Edition

Aspectow Edge Edition is a lightweight, ultra-fast non-servlet runtime platform built on the Aspectran framework, specifically optimized for high-performance microservices and REST API services.

By completely eliminating traditional servlet and JSP specifications, Aspectow Edge achieves an ultra-lean runtime footprint, lightning-fast startup times, and minimal memory consumption. Powered by **Netty** for non-blocking asynchronous network I/O and **Java 21 Virtual Threads (Project Loom)** for sequential, thread-safe business execution, it delivers massive concurrency and throughput without the code complexity and cognitive overhead of reactive programming (Mono/Flux).

## Key Features

- **Netty Asynchronous I/O Engine**: Leverages Netty's battle-tested event loop architecture and OS-native transports (Linux epoll, macOS kqueue) for extreme connection scalability and low latency.
- **Java 21 Virtual Threads Integration**: Dispatches assembled HTTP requests directly into lightweight virtual threads, eliminating carrier OS thread exhaustion while allowing clean, sequential, synchronous Aspectran code (Translets, Actions, MyBatis, JPA).
- **Non-Servlet Architecture**: A streamlined core without the heavy legacy overhead of the servlet container or JSP compilers.
- **Dynamic Content Compression**: Built-in support for Gzip, Deflate, Brotli, and Zstandard compression with selective MIME type and content size filtering.
- **Access Logging**: Flexible HTTP access logging supporting Combined, Common, and customizable logging formats with async appenders.
- **WebSocket Support**: High-performance per-context WebSocket handling.
- **Built on Aspectran**: Full access to Aspectran's declarative Translet architecture, AOP, IoC, Bean management, and adaptive session clustering.
- **Ideal for Cloud-Native Microservices**: Fast container startup and low memory footprint make it exceptionally well suited for Docker and Kubernetes environments.

## Requirements

- Java 21 or later
- Maven 3.9.4 or later

## Building from Source

Follow these steps to build Aspectow Edge Edition from the source code:

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/aspectran/aspectow-edge.git
    ```

2.  **Navigate to the project directory:**
    ```sh
    cd aspectow-edge
    ```

3.  **Build the project with Maven:**
    This will compile the source code, package the application, and copy runtime dependencies to `app/lib`.
    ```sh
    mvn clean package
    ```

## Running the Server

Once the project is built, you can start the server using the Aspectran Shell or as a background daemon.

### Interactive Shell Mode

1.  **Navigate to the `bin` directory:**
    ```sh
    cd app/bin
    ```

2.  **Start the Aspectran Shell:**
    ```sh
    ./shell.sh
    ```
    This will launch an interactive terminal for managing and inspecting the Netty server and Aspectran components.

3.  **Access the application:**
    Once the server is running, you can access the default web application in your browser at [http://localhost:8081](http://localhost:8081).

### Background Daemon Mode

To run as a background service:
```sh
cd app/bin
./daemon.sh start
```

Commands: `start`, `stop`, `restart`, `status`.

## Contributing

We welcome contributions! If you'd like to contribute, please fork the repository and submit a pull request. For major changes, please open an issue to discuss your ideas.

## License

Aspectow Edge Edition is licensed under the [Apache License 2.0](LICENSE.txt).
