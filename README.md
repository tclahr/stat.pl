# stat.pl - A Simple Perl Script for File Metadata Extraction

[![GitHub License](https://img.shields.io/github/license/tclahr/stat.pl?color=blue)](https://github.com/tclahr/stat.pl/blob/main/LICENSE)

## Overview

**`stat.pl`** is a lightweight and efficient Perl script that extracts and displays file statistics in a pipe-delimited format. It is especially useful for system administrators, digital forensics experts, and developers who need a quick way to analyze file metadata such as inode, permissions, ownership, size, and timestamps in Unix-based systems.

With its human-readable and machine-parsable output, `stat.pl` helps streamline log generation, batch file analysis, and integration into other tools and pipelines.

## Features

- 📄 **Pipe-delimited output** for easy parsing and automation.
- 🧾 **Supports multiple files and directories** as input.
- 🔍 **Displays symlink targets** for symbolic links.
- 🧑‍💻 **Outputs essential file metadata**, including:
  - Inode number
  - File permissions (e.g., `-rwxr-xr-x`)
  - UID / GID
  - File size (bytes)
  - Timestamps (`atime`, `mtime`, `ctime`) as Unix timestamps
- ✅ Minimal dependencies – just standard Perl!

## Usage

```bash
stat.pl [OPTIONS] FILE...
```

### Examples

```bash
stat.pl file.txt
stat.pl /etc/passwd /bin/ls
stat.pl /usr/bin/*
```

### Output Format

Each line of output follows this structure:

```text
0|filename|inode|mode|uid|gid|size|atime|mtime|ctime|0
```

#### Field Descriptions

- **filename** – File path (with symlink target if applicable)
- **inode** – Inode number
- **mode** – File type and permissions
- **uid** – User ID of the owner
- **gid** – Group ID of the owner
- **size** – File size in bytes
- **atime** – Last access time (Unix timestamp)
- **mtime** – Last modification time (Unix timestamp)
- **ctime** – Last status change time (Unix timestamp)

> 📝 Note: Symbolic links are resolved to show both link and target.

## Requirements

- **Perl** (version 5 or higher)
- Compatible with Linux, macOS, and other Unix-like systems

## License

This project is licensed under the **Apache License 2.0**.  
See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome!

If you'd like to add features, improve compatibility, or fix bugs:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -am 'Add new feature'`
4. Push to your fork: `git push origin feature-name`
5. Submit a pull request
