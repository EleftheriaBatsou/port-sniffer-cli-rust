## Port Sniffer CLI - RUST

This program uses asynchronous tasks (tokio) to scan a range of ports on a specified IP address, leveraging the TcpStream for port connectivity checks. 
It provides a structured way to handle command-line arguments (bpaf) and demonstrates the power of Rust's asynchronous programming model for network applications.

_Let's have a quick overview of what this program is about:_

**Dependencies**
- bpaf: This is used for parsing command-line arguments (Bpaf is a struct that derives clap's FromArgs trait).
- io: Standard library for input/output operations.
- net: Network primitives for working with IP addresses and TCP streams.
- mpsc: Multi-producer, single-consumer channels for communication between threads.
- tokio: Asynchronous runtime for Rust, used for async tasks and networking operations.

**Constants and Configuration**
- MAX: Maximum port number to scan.
- IPFALLBACK: Default IP address to use if none is provided.

**Arguments**
- address: IP address to sniff (defaulting to IPFALLBACK if not provided).
- start_port: Starting port number for scanning (defaulting to 1).
- end_port: Ending port number for scanning (defaulting to MAX).

- start_port_guard: Helper function to validate that the start port is greater than 0.
- end_port_guard: Helper function to validate that the end port is less than or equal to MAX.

**Build and Run the Program**

Use `cargo run` to build and run your program. Cargo will automatically handle fetching dependencies and compiling the project.

When running the program, you can provide command-line arguments as required. For example:

`cargo run -- --address 192.168.1.1 --start 1 --end 1000`

Replace 192.168.1.1 with the IP address you want to scan, and adjust the --start and --end arguments to specify the range of ports to scan.
