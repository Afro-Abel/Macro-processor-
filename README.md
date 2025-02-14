# State Machine Macro Processor

## Description

# A TeX-like Macro Processor

## Assignment Description

TeX (or its later evolution LaTeX) is a program used often in academia to write technical papers and documents. Users define macros in text files that also contain the contents of the document, and TeX processes macros and string expands them based on their definitions.

This project implements a state machine for processing macros in a text stream. The macro processor parses the input and handles various predefined commands like `def`, `undef`, `if`, `ifdef`, `expandafter`, and `include`. The goal is to transform and manipulate text based on user-defined macros and handle special characters through an escape mechanism.

The state machine processes input line by line and can handle multiple macro commands, allowing macros to be defined, undefined, and expanded dynamically.

---

## Features

- **Macro Expansion**: Supports the definition (`def`), undefinition (`undef`), and expansion (`expandafter`) of macros.
- **Conditional Compilation**: Handles conditional statements like `if` and `ifdef`.
- **Escaping Characters**: Uses a backslash (`\`) escape mechanism for special characters (e.g., `{`, `}`, `%`, `#`, etc.).
- **File Inclusion**: Includes external files and processes them as part of the input using the `include` command.
- **Macro Handling**: Supports user-defined macros and built-in macro names.

---

## States

The state machine operates in the following states:

1. **PLAIN**: The default state where plain text is processed. Characters are added to the output unless they are escaped.
2. **MACRO_NAME**: This state handles the parsing of macro names. When a macro is identified, the state transitions to the corresponding macro state (e.g., `DEF`, `UNDEF`, `IF`, `IFDEF`).
3. **DEF**: Defines a new macro. Takes two arguments: the macro name and its value.
4. **UNDEF**: Undefines a previously defined macro.
5. **IF**: Conditional compilation based on the value of a macro.
6. **IFDEF**: Conditional compilation if a macro is defined.
7. **EXPANDAFTER**: Expands macros after processing the specified arguments.
8. **INCLUDE**: Includes external files and processes them as part of the input.

---

## Setup

To use this project, you need to have a C environment set up that can compile and run the code. Below are the setup instructions:

### Prerequisites

- A C compiler (e.g., GCC)
- Basic knowledge of C and memory management
