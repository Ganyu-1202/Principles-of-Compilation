# Principles-of-Compilation
Principles of Compilation

## Compilation Principles (Pre-Exam Review)

### 1. Compiler Overview
- **Compiler**: translates high-level source code into target code (usually assembly or machine code).
- **Interpreter**: executes source program directly, statement by statement.
- Typical phases:
  1. Lexical analysis
  2. Syntax analysis
  3. Semantic analysis
  4. Intermediate code generation
  5. Code optimization
  6. Target code generation

### 2. Lexical Analysis
- Input: character stream
- Output: token stream
- Main tasks:
  - Remove whitespace/comments
  - Recognize identifiers, keywords, constants, operators, delimiters
  - Record identifiers in a symbol table
- Core models:
  - Regular expressions describe token patterns
  - Finite automata (NFA/DFA) implement scanning

### 3. Syntax Analysis
- Input: token stream
- Output: parse tree / abstract syntax tree (AST)
- Grammar basics:
  - **CFG**: terminals, non-terminals, productions, start symbol
- Common parser types:
  - Top-down (LL)
  - Bottom-up (LR, SLR, LALR)
- Key exam topics:
  - Eliminate left recursion
  - Left factoring
  - FIRST/FOLLOW sets
  - Predictive parsing table
  - Shift-reduce conflicts

### 4. Semantic Analysis
- Checks whether syntax-correct code is meaningful.
- Typical checks:
  - Type checking
  - Scope and declaration checking
  - Function parameter matching
  - Control-flow validity (`break`, `return`, etc.)
- Attribute grammars:
  - **Synthesized attributes** pass info bottom-up
  - **Inherited attributes** pass info top-down/sideways

### 5. Intermediate Representation (IR)
- Purpose: machine-independent program form for analysis/optimization.
- Common forms:
  - Three-address code (TAC)
  - Quadruples / triples
  - SSA (Static Single Assignment)
- Frequent TAC forms:
  - `x = y op z`
  - `x = op y`
  - `if x relop y goto L`
  - `goto L`

### 6. Runtime Environment & Symbol Table
- Symbol table stores:
  - name, type, scope, storage class, address/offset, parameter info
- Runtime memory layout:
  - Code segment
  - Static/global area
  - Heap
  - Stack (activation records/call frames)
- Activation record often includes:
  - Parameters, return address, control link, local variables, temporaries

### 7. Code Optimization
- Goal: improve performance/space without changing semantics.
- Machine-independent optimizations:
  - Constant folding
  - Common subexpression elimination
  - Dead code elimination
  - Copy propagation
  - Loop-invariant code motion
- Basic-block and flow-graph analysis are foundational.

### 8. Target Code Generation
- Maps IR to assembly/machine instructions.
- Key concerns:
  - Instruction selection
  - Register allocation/spilling
  - Instruction scheduling
- Trade-off:
  - Better code quality often increases compile time.

### 9. High-Frequency Exam Checklist
- Distinguish lexical vs syntax vs semantic errors.
- Convert regex -> NFA -> DFA (and minimize DFA when required).
- Build FIRST/FOLLOW and LL(1) table.
- Perform LR shift/reduce steps from a parsing table.
- Generate TAC for arithmetic/boolean/control-flow statements.
- Identify optimization opportunities in a basic block.
