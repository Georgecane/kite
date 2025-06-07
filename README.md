# Kite

Kite is a programming language designed for Digital Signal Processing (DSP) and Audio Processing, with an emphasis on real-time capabilities, efficiency, and ease of integration with existing audio workflows.

**Note:** The current reference implementation of the Kite compiler is written in Python and uses LLVM as its backend.

## Features

- **High Performance:** Compiles to efficient native code via LLVM.
- **Real-Time Capabilities:** Suitable for real-time signal processing with low latency.
- **Modularity:** Supports extensibility with clear, maintainable language constructs.
- **Cross-Platform:** Output executables for Windows, Linux, and macOS.
- **Easy Compilation:** The Python-based compiler automatically generates LLVM IR and can invoke native toolchains (clang/gcc) to build executables.

## Design Goals

- **Efficiency:** Provide a lean, performant language for computationally heavy DSP tasks.
- **Expressiveness:** Enable developers to write easy-to-read code that translates directly into high-performance operations.
- **Integration:** Seamlessly integrate with existing audio libraries and systems, enhancing traditional DSP workflows.

## Getting Started

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Georgecane/kite.git
   ```

2. **Install Requirements**
   - Python 3.9+ and `llvmlite`, `ply`
   - LLVM toolchain (`clang` or `gcc`) available in your PATH

   ```bash
   pip install llvmlite ply
   ```

   > On Windows, you may need to install LLVM (e.g., via Chocolatey: `choco install llvm`) or use MSYS2 for native compilation.

3. **Compile a Kite Program**
   - Write your Kite source file, e.g. `test.kit`
   - Compile and build a native executable:
     ```bash
     python kitecomp.py test.kit
     ```
   - This will:
     - Generate `test.ll` (LLVM IR)
     - Automatically invoke `clang` or `gcc` to produce the executable (`test` or `test.exe`)

4. **Run the Executable**
   ```bash
   ./test      # Linux/macOS
   test.exe    # Windows
   ```

5. **Explore Examples**
   - Check out the provided examples and tests to see Kite in action for DSP and audio processing scenarios.

## Example

```c
int main() {
    int i = 0;
    do {
        i = i + 1;
    } while (i < 10);
    return i;
}
```

## Contributing

Contributions are welcome! If you have ideas for new features or improvements, please open an issue or submit a pull request.

## License

This project is licensed under the Apache 2.0 License.
