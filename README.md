# C Scanner & Recursive-Descent Parser

A clean, professional, and developer-friendly README describing a simple educational compiler front-end consisting of a scanner and a recursive-descent parser. This document has been polished for clarity, consistency, and readability.

---

# 📘 Project Overview

This project provides two Python utilities and an example C source file designed to demonstrate the basic structure of a compiler front-end:

* **Scanner** — A lexical analyzer that tokenizes a C-like source file and writes the tokens to a text file.
* **Parser (Top-Down)** — A recursive-descent parser that processes the token file and reports whether the input is syntactically valid.
* **Example Source File** — A simple `int main()` program used for testing.

> These tools are educational and showcase scanner–parser interaction. They are not intended to be a complete or fully compliant C compiler.

---

# 📂 Repository Structure

```
project/
│
├── scanner.py               # Lexical scanner
├── test_tokens.txt          # output of scanner 
├── parser_Top_down.py      # Recursive-descent parser
├── test.c                # Test C source file
└── README.md



# 🚀 Quick Start: Running the Scanner

To tokenize a C source file, run the scanner:

```bash
python scanner.py test.c
```

Expected output:

```
Tokens saved to: test_tokens.txt
```

A token file named `test_tokens.txt` will be created in the same directory.

---

# 🚀 Quick Start: Running the Parser

After generating the token file, run the parser:

```bash
python parser_Top_down.py test_tokens.txt
```

### Example Parser Outputs

**Successful parse:**

```
Parsing Completed Successfully. No Syntax Errors Found.
```

**Syntax error example:**

```
Syntax Error! Expected: (;) but found: (Type: IDENTIFIER, Value: x) at token index 12
```

**Stopped early warning:**

```
Warning: Parsing stopped early at token index <n>. Check for unparsed tokens.
```

---

# 🧪 Example Run

Below is an example demonstrating how the **scanner** and **parser** operate on a sample C program.

## 📝 Input Code

```c
int main() {
    int x, y;
    // This is a single-line comment
    if (x == 42) {
        /* block comment */
        x = x - 3;
    } else {
        y = 3.1; // Another comment
    }
    return 0;
}
```

The scanner will tokenize this input and generate a structured **token file**.
Running the parser on this token file will confirm whether the syntax is valid
according to the supported grammar.


# 📄 Token File Format

The scanner generates a structured, human-readable token table, for example:

```
#    TYPE                 VALUE
==================================================
1    KEYWORD              int
2    KEYWORD              main
3    SPECIAL_CHARACTER    (
...
Total tokens: 38
```

The parser:

* Ignores `COMMENT` tokens.
* Expects the token *type* in the second column and the *value* in the third column.

---

# 🔎 Supported Features

## Scanner Capabilities

* `KEYWORD` tokens (e.g., `int`, `return`, `if`, `else`, `float`, `main`)
* `IDENTIFIER`
* `NUMERIC_CONSTANT` (integers and floating-point values)
* `OPERATOR` tokens (`+`, `-`, `*`, `/`, `==`, `!=`, `<=`, `>=`, etc.)
* `SPECIAL_CHARACTER` tokens (`(){}[],;`)
* `COMMENT` tokens (`//...` and `/* ... */`)

## Parser Capabilities

* Function definition: `int main() { ... }`
* Variable declarations
* Assignment statements
* Arithmetic expressions using `+` and `-`
* Relational expressions (`==`, `!=`, `<`, `>`, `<=`, `>=`)
* Conditional statements: `if (...) { ... } else { ... }`
* Return statements: `return <value> ;`

---

# 💡 Helpful Tips

* Use `test.c` to quickly verify scanner and parser integration.
* If a syntax error appears, refer to the token index reported by the parser.
* Do not manually alter column alignment in token files, as the parser relies on the expected structure.

---


# ✍ Author

Hussien Habeeb
---

