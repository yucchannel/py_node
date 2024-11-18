# PN Launcher V6

PN Launcher V6 is a Python-based application that interprets and executes a custom programming language (`.pn` files). It includes a graphical interface built with Tkinter and features a lexer, parser, and interpreter for processing `.pn` files efficiently.

---

## Features

- **Lexer**: Tokenizes `.pn` code into manageable tokens.
- **Parser**: Builds an Abstract Syntax Tree (AST) from the tokens.
- **Interpreter**: Executes the AST with optimized memory management.
- **Graphical Interface**: Simple Tkinter-based GUI for running `.pn` files.
- **Multithreading**: Runs code in a separate thread to keep the interface responsive.

---

## Requirements

- **Python Version**: 3.8 or higher
- **Dependencies**: 
  - `tkinter` (usually bundled with Python)
  - Standard Python libraries: `os`, `re`, `threading`, `time`

---

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/pn-launcher-v6.git
   cd pn-launcher-v6
   ```

2. Run the application:

   ```bash
   python pn_launcher_v6.py
   ```

---

## Usage

1. Launch the application:

   ```bash
   python pn_launcher_v6.py
   ```

2. Enter a command in the GUI's input field:
   - **To execute a `.pn` file**: Use the `start <filename>` command.
     Example:
     ```
     start example.pn
     ```
   - **Unknown commands** will display an error message in the output area.

3. The program will interpret the `.pn` file and display any results in the output section.

---

## File Requirements

- Files must have a `.pn` extension.
- Ensure the `.pn` file is in the correct directory and contains valid code.

---

## Code Structure

### Lexer

The `Lexer` tokenizes the input code using a lazy evaluation approach. The supported tokens include keywords, variables, and symbols.

```python
pattern = r'\s*(let|const|var|delete|print|console\.log|if|else|switch|case|default|for|while|do|function|return|call|async|await|Promise|push|pop|shift|unshift|slice|splice|new|Object\.assign|Object\.keys|[a-zA-Z_]\w*|[0-9]+|".*?"|[=+();{}])\s*'
```

### Parser

The `Parser` processes tokens into an Abstract Syntax Tree (AST). The current implementation supports:
- Variable assignments (`let`, `const`, `var`)
- Print statements (`print`, `console.log`)
- `if` conditions
- Basic `for` loops

### Interpreter

The `Interpreter` executes the AST while managing memory with the `OptimizedMemory` class. This class handles variables efficiently by storing only necessary data.

---

## Example `.pn` Code

```plaintext
let x = 10;
let y = 20;
print x;
if y {
  print y;
}
```

---

## Known Limitations

- Only basic constructs like `let`, `print`, `if`, and `for` loops are supported.
- Error handling for invalid syntax is minimal.
- Currently designed for single-threaded logic within the interpreter.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Contributing

Contributions are welcome! Please open an issue or submit a pull request to discuss potential changes.

---


```
