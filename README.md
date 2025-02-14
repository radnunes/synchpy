Synchpy - Backup/Replica Synchronization Program

Requirements:
- One-way synchronization: Source remains unchanged; replica matches source.
- Periodic synchronization:
  - Without timer flag: Runs once.
  - With timer flag: Periodically runs (set interval in minutes or hours).
- File operations (create, copy, remove) should be logged:
  - Console output logging with flag `--log`.
  - Log file created in replica folder (with `.log` extension), or specified via `--logfile <path>`.
  - Log entries appended to file, not overwritten.
- Folder/file comparison:
  - Check if source file exists in replica.
  - Compare MD5 hashes for files in source and replica. If different, update replica.
  - Folders are checked recursively, applying same logic to files inside.

Additional Considerations:
- Error handling: Manage missing paths, permission issues, and file operation failures.
- Performance: Consider caching MD5 hashes for large directories.
- Cross-platform support: Ensure compatibility across Windows, macOS, Linux.
- Command-line arguments:
  - `--source`: Source directory.
  - `--replica`: Replica directory.
  - `--log`: Enable console logging.
  - `--logfile <path>`: Log file path.
  - `--timer <interval>`: Synchronization interval (e.g., `30m`, `1h`).

