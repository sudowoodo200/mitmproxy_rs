## Unreleased

- Implement `is_closing(self) -> bool` method on `TcpStream` to match `asyncio.StreamWriter`.

## 0.1.9

- Simplified GitHub actions for CI and publishing wheels to PyPI.
- Failed sub-tasks are now handled immediately and cause a server shutdown
  instead of silently returning and only yielding an error when shutting down
  the server manually.

## 0.1.8

- Fix building binary wheels for `aarch64-unknown-linux-gnu`.

## 0.1.7

- Do not exit the network task when a draining TcpStream is already closed. 
- Make log messages for "no current WireGuard session" more user-friendly.
- Attempt to build binary wheels for `aarch64-unknown-linux-gnu` for Raspberry
  Pi support.

## 0.1.6

- Fix test client to only send valid packets.

## 0.1.5

- Adapt the test client to handle EAGAIN gracefully.

## 0.1.4

- Split test client into separate workspace crate to speed up builds and
  and hopefully fix them on macos.

## 0.1.3

- Adapt test client to produce packets with correct checksums.
- Build test client binaries in the `publish` GitHub Action.
- Stop building binary wheels for 32-bit Linux and Windows targets.
- Validate TCP checksums and reject invalid incoming packets early.
- Lower priority of log messages for non-fatal `TcpStream` cleanup errors during
  server shutdown.

## 0.1.2

- Revert addition of `ChecksumCapabilities::ignored` to the virtual network device.
  This change in v0.1.1 completely broke TCP connection handling.

## 0.1.1

- Added a simple test client binary (`mitm-wg-test-client`).
- Ignore TCP checksums in network device code, they are already checked in other places.
- Port to boringtun v0.5.

## 0.1.0

Initial Release.