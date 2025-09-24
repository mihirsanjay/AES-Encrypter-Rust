# Rust Crypter
x86-64 Malware Crypter built in Rust for Windows with Anti-VM, powered by memexec

## Usage

### Single File
1. Put your .exe in `/crypt/`
2. `cd crypt && cargo run <filename.exe>`
3. `mv encrypted_Input.bin key.txt ../stub/src/`
4. `cd ../stub && cargo build --target x86_64-pc-windows-gnu --release`
5. Your encrypted exe is in `stub/target/x86_64-pc-windows-gnu/release/stub.exe`

### Batch Processing (Multiple Files)
```bash
./batch.sh /path/to/folder/with/exe/files
```
Output: `batch_output/` folder with `{filename}_encrypted.exe` files

### Supported targets
- Windows x86-64
- Windows x86

### Limitations
- .NET not supported
- Files over 600MB not supported

## TODO
- File dialogue choose file instead of renaming code strings/executable names
- Automatically move encrypted bytes and key into stub for compiling
- GUI
- Obfuscated Strings

## Disclaimer
This is a tool used to test the Static + Dynamic detection capabilites of AV and EDR, use of this project is at your own risk

## MITRE TTPs (Indicators)
- User Execution: Malicious File T1204.002
- Deobfuscate/Decode Files or Information T1140
- Embedded Payloads T1027.009
- System Checks T1497.001
- Reflective Code Loading T1620
- Boot or Logon Autostart Execution: Registry Run Keys / Startup Folder T1547.001

## References
https://crates.io/crates/memexec
https://crates.io/crates/inside-vm
