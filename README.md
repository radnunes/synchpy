# Synchpy - Backup/Replica Synchronization Program

## Requirements

- **One-way synchronization**: The source remains unchanged; the replica matches the source.
- **Periodic synchronization**:
  - Without the timer flag: Runs once.
  - With the timer flag: Runs periodically (set interval in minutes or hours).
- **File operations (create, copy, remove) should be logged**:
  - Console output logging with the flag `--log`.
  - A log file is created in the replica folder (with `.log` extension), or specified via `--logfile <path>`.
  - Log entries are appended to the file, not overwritten.
- **Folder/file comparison**:
  - Check if the source file exists in the replica.
  - Compare MD5 hashes for files in the source and replica. If different, update the replica.
  - Folders are checked recursively, applying the same logic to files inside.

## Additional Considerations

- **Error handling**: Manage missing paths, permission issues, and file operation failures.
- **Performance**: Consider caching MD5 hashes for large directories.
- **Cross-platform support**: Ensure compatibility across Windows, macOS, and Linux.
- **Command-line arguments**:
  - `--source`: Source directory.
  - `--replica`: Replica directory.
  - `--log`: Enable console logging.
  - `--logfile <path>`: Log file path.
  - `--timer <interval>`: Synchronization interval (e.g., `30m`, `1h`).
