# Project roadmap

A standard compiler typically works in phases: turning text into tokens, tokens into a tree, the tree into an intermediate representation, and finally into machine code.

Here is a roadmap of real-world, applied projects that will take you from the basics of parsing to advanced code generation and optimization.

---

### Phase 1: The Basics (Front-End & Parsing)

_Focus: Lexical analysis (tokenization), syntax analysis (parsing), and Abstract Syntax Trees (AST)._

- **Linter and Parser:**
  - **The Project:** Write a program from scratch that takes a markup string (JSON, TOML, YAML, etc...), tokenizes it (braces, brackets, strings, numbers), parses it into an AST, and then either evaluates it into native language objects or prints out specific syntax errors (linting).
  - **What you learn:** Building a lexer and a recursive descent parser. It’s highly practical because JSON is ubiquitous, and standard libraries hide how it actually works.
- **Math Expression Evaluator (with Variables):**
  - **The Project:** Build a command-line calculator that can handle operator precedence (PEMDAS) and variables (e.g., `let x = 5 * (10 + 2); x / 2`).
  - **What you learn:** Dealing with operator precedence, the Shunting Yard algorithm or Pratt parsing, and basic environment management (storing variables in a symbol table).
- **HTML/Text Template Engine:**
  - **The Project:** Build a basic template engine (like Jinja or Handlebars) that takes a text file with embedded tags (e.g., `{{ variable }}`, `{% if condition %}`) and compiles it down to a static HTML file based on provided data.
  - **What you learn:** Mixing text data with control flow, string manipulation, and AST interpretation.

---

### Phase 2: Intermediate (Bytecode, VMs, and Transpilers)

_Focus: Semantic analysis, type checking, intermediate representations (IR), and execution environments._

- **Markdown to HTML Transpiler:**
  - **The Project:** Read a Markdown file, build an AST, and generate valid HTML. To make it harder, add support for custom extensions (like specific table formats or callout boxes).
  - **What you learn:** The Visitor pattern for traversing trees, and Source-to-Source compilation (transpiling), which is exactly how tools like Babel (JavaScript) or TypeScript work.
- **Brainfuck Ahead-of-Time (AOT) Compiler:**
  - **The Project:** Brainfuck is a notoriously simple language with only 8 commands. Write a compiler that reads Brainfuck code and outputs actual, runnable Assembly code (e.g., x86-64 or ARM) or a C file.
  - **What you learn:** Emitting actual lower-level code, mapping high-level instructions to CPU registers, and basic optimizations (like combining consecutive `+` commands into a single add instruction).
- **Bytecode Virtual Machine (VM) for a Lisp Dialect:**
  - **The Project:** Design a simple Lisp-like language. Instead of evaluating the AST directly, compile the AST into custom "bytecode" (instructions for a fake CPU) and write a Virtual Machine in C or Rust to execute that bytecode.
  - **What you learn:** Stack-based execution models, instruction decoding, garbage collection basics, and the architecture behind languages like Python, Java, and C#.

---

### Phase 3: Advanced (Native Code, LLVM, and Optimizations)

_Focus: Code generation, LLVM framework, register allocation, and performance optimization._

- **Domain-Specific Language (DSL) for Querying Logs:**
  - **The Project:** Build a typed query language (similar to SQL or PromQL) tailored for filtering massive local log files. It should compile the query into a highly optimized, single-purpose execution plan.
  - **What you learn:** Type checking (ensuring users don't try to add a string to an integer), query optimization (pruning dead branches of the AST), and building something that solves a direct, real-world DevOps problem.
- **Statically Typed Language to WebAssembly (Wasm):**
  - **The Project:** Invent a small, statically typed language (let's call it "Mini-C") and write a compiler that outputs standard WebAssembly binaries (`.wasm`). Run your compiled language directly in the browser.
  - **What you learn:** The WebAssembly specification, binary encoding, linear memory management, and modern web compiler targets.
- **A Subset of C (or Go) using LLVM:**
  - **The Project:** Use the LLVM framework as your backend. You write the lexer and parser for a subset of C (handling functions, loops, structs, and pointers), generate LLVM Intermediate Representation (IR), and let LLVM compile it to highly optimized native machine code.
  - **What you learn:** Professional compiler infrastructure. LLVM is the industry standard (powering Clang, Rust, Swift). You'll learn about Static Single Assignment (SSA) form, basic blocks, and advanced compiler passes.

---

Would you like me to break down the first steps for building the JSON parser, or would you prefer to explore the architecture of the Bytecode Virtual Machine?
