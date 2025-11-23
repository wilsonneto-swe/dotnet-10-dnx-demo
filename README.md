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

## Installing and/or Execution

Install as a global .NET tool via NuGet:

```bash
// to install
dotnet tool install --global PassGenCli

// to just run
dnx passgencli
```

## License

MIT License - See LICENSE file for details

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## Requirements

- .NET 10.0 or higher
