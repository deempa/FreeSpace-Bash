# FreeSpace

FreeSpace is a Bash script that allows you to compress files and directories, freeing up disk space. It provides options for recursive compression and setting a timeout for deleting compressed files.

## Usage

```
freespace [-r] [-t ###] file [file...]
```

## Options

- `-r`: Enables recursive compression. If this flag is set, the script will compress all files and subdirectories within a directory.
- `-t ###`: Sets the timeout in hours. After the specified timeout, compressed files will be deleted. The default timeout is 48 hours.

## Functions

### `is_file_zipped`

Checks if a file is already compressed. If it is, and it meets the timeout condition, the file will be deleted.

### `zip_directory_without_recursive`

Compresses files in a directory without recursively compressing subdirectories.

### `zip_directory_with_recursive`

Recursively compresses files in a directory, including all subdirectories.

### `zip_file`

Compresses a single file. If the file is already compressed, it will be renamed with the prefix "fc-" and a timestamp.

### `start_zipping`

Determines whether to perform recursive or non-recursive compression based on the options provided. It calls the appropriate functions accordingly.

## Example Usage

Compress a single file:

```
freespace myfile.txt
```

Compress a directory without recursion:

```
freespace -r mydirectory/
```

Compress a directory with recursion:

```
freespace -t 24 -r mydirectory/
```

## Note

Please note that this script permanently deletes files after the specified timeout. Use it with caution and ensure you have proper backups in place.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
