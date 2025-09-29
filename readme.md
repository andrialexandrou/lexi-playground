# Welcome to Lexi - English-to-Code Compiler

Lexi compiles plain English descriptions into working code in any programming language.

## Quick Start (Copy & Paste These Commands)

### 1. Configure Lexi with your API key

**For Anthropic Claude (recommended):**
```bash
lexi config set provider anthropic
lexi config set model claude-3-5-sonnet-20241022
lexi config set api_key YOUR_API_KEY_HERE
```

**For OpenAI GPT:**
```bash
lexi config set provider openai
lexi config set model gpt-4
lexi config set api_key YOUR_API_KEY_HERE
```

### 2. Test it out

```bash
# Create a simple test program
echo "Create a function that adds two numbers together" > add.lxi

# Compile to JavaScript
lexi compile add.lxi --target javascript

# View the generated code
cat add.js
```

## Try Different Languages

```bash
# Python
echo "Create a function that checks if a number is prime" > prime.lxi
lexi compile prime.lxi --target python
python prime.py

# Rust
echo "Create a function that calculates factorial" > factorial.lxi
lexi compile factorial.lxi --target rust
rustc factorial.rs && ./factorial

# Go
echo "Create a function that reverses a string" > reverse.lxi
lexi compile reverse.lxi --target go
go run reverse.go

# SQL
echo "Create a table for blog posts with title, content, author, and timestamps" > blog.lxi
lexi compile blog.lxi --target sql
cat blog.sql
```

## Complex Example - Node CLI Tool

```bash
cat > password-gen.lxi << 'EOF'
Build a command-line password generator that accepts length and complexity options.
Include uppercase, lowercase, numbers, and symbols.
Add options for excluding similar characters and provide verbose output.
EOF

lexi compile password-gen.lxi --target javascript
node password-gen.js
```

## Profile Management (Multiple API Keys)

```bash
# Create work profile
lexi profile create work
lexi config set provider anthropic
lexi config set api_key YOUR_WORK_KEY

# Create personal profile
lexi profile create personal
lexi config set provider openai
lexi config set api_key YOUR_PERSONAL_KEY

# Switch between profiles
lexi profile use work
lexi profile use personal

# List all profiles
lexi profile list
```

## Available Commands

```bash
lexi --help                          # Show all commands
lexi compile <file.lxi>              # Compile to JavaScript (default)
lexi compile <file.lxi> -t python    # Compile to specific language
lexi compile <file.lxi> --run        # Compile and run immediately
lexi config list                     # Show current configuration
lexi profile list                    # Show all profiles
```

## Supported Languages

- JavaScript (Node.js)
- Python
- Java
- C++
- Rust
- Go
- SQL
- MongoDB
- Redis

## Get API Keys

- **Anthropic Claude:** https://console.anthropic.com/
- **OpenAI GPT:** https://platform.openai.com/api-keys

## More Examples

Check out `docs/examples.md` for more complex programs including:
- Web servers
- Database queries
- Browser automation tests
- Data processing pipelines
- And more!

## Need Help?

- Documentation: https://github.com/andrialexandrou/lexi/tree/main/docs
- Issues: https://github.com/andrialexandrou/lexi/issues
