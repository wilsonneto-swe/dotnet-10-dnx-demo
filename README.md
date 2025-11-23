# DNX - .Net 10 New Features

DNX is a new tool/script delivered with the .Net 10, the purpose of this tool is to make super simpler the .Net tools execution, without needing even the installation of the tool.

Fot those familiar with python and/or javascript, it is similar to `npx`, `uvx` or `pipx`.

## How to use it?

Just use the `dnx [package-name]` tool. Example:

```bash
# passgencli is the example app in this repo, created for this demo
dnx passgencli
```

---

# PassGen - Secure Password Generator
A lightweight, secure CLI tool for generating cryptographically strong passwords with customizable options.

> Nuget Package: https://www.nuget.org/packages/PassGenCli


## Features

- Generates cryptographically secure passwords using `System.Security.Cryptography.RandomNumberGenerator`
- Customizable password length
- Exclude specific characters to meet policy requirements
- No external dependencies - pure C# implementation
- Cross-platform support (.NET 10.0)

## Installation

Install as a global .NET tool via NuGet:

```bash
dotnet tool install --global PassGenCli
```

## Usage

### Basic Usage

Generate a password with default settings (16 characters):

```bash
passgen
```

### Specify Length

Generate a password with a specific length:

```bash
passgen -l 32
passgen --length 24
```

### Exclude Characters

Exclude specific characters from the generated password:

```bash
# Exclude commonly confused characters
passgen --length 20 --exclude "0O1lI"

# Exclude special characters that might cause issues
passgen -l 16 -e "{}[]"

# Exclude quotes for shell-friendly passwords
passgen -l 20 -e "\"'"
```

### Help

Display usage information:

```bash
passgen --help
passgen -h
```

## Character Sets

By default, passwords are generated from the following character sets:

- **Uppercase letters**: A-Z
- **Lowercase letters**: a-z
- **Digits**: 0-9
- **Special characters**: !@#$%^&*()_+-=[]{}|;:,.<>?

## Security

- Uses `RandomNumberGenerator` from `System.Security.Cryptography` for cryptographically secure random number generation
- Implements proper distribution across all available characters
- No predictable patterns or biases in password generation

## Examples

```bash
# Generate a 32-character password
passgen -l 32

# Generate a password without ambiguous characters
passgen --length 20 --exclude "0O1lI"

# Generate a database-safe password (no special chars that might need escaping)
passgen -l 24 -e "\"'`\\;|&$"

# Generate a 16-character password excluding brackets
passgen -l 16 -e "{}[]()<>"
```

## Building from Source

```bash
# Clone the repository
git clone https://github.com/wilsonneto-swe/passgen-cli.git
cd passgen-cli

# Build the project
dotnet build

# Run locally
dotnet run -- -l 20

# Pack as NuGet package
dotnet pack

# Install locally
dotnet tool install --global --add-source ./bin/Debug PassGenCli
```

## License

MIT License - See LICENSE file for details

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## Requirements

- .NET 10.0 or higher
