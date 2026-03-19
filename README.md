# haoen

## haoen firmware CVE poc

### Prerequisites
- Python 3
- `nc` (netcat)

## Step-by-Step Testing Instructions

### Step 1: First Run (Check Bypass)
Run the PoC to verify the command bypasses security checks.
Expected output: ✓ BYPASS SUCCESSFUL - the command passes all security checks

### Step 2: Setup Listener (New Terminal Window)
Open a **NEW terminal window** and run:

```bash
nc -l 1111
```

This starts a listener on port 1111. Leave this terminal open and waiting.

### Step 3: Execute Reverse Shell (Original Terminal)

In your original terminal, run:

```bash
./reverse_shell_poc.py --execute
```

When prompted, type `yes` and press Enter.

### Step 4: Verify Connection

Switch to the terminal with the netcat listener (from Step 2). You should now have a shell prompt!

Try commands like:
- `whoami` - see your username
- `pwd` - see current directory
- `ls` - list files
- `exit` - close the connection

## What's Happening?

1. **Bypass Technique**: Uses `python3` to execute arbitrary code
2. **Why It Works**: `python3` is NOT in the blocked commands list
3. **Security Impact**: Full command execution despite security checks

## The Vulnerability

The `check_safe()` function blocks commands like:
- `sudo`, `rm -rf /`, `chmod`, `curl | bash`, etc.

But it **does NOT block**:
- `python3` (arbitrary code execution)
- `nc` (netcat - network connections)
- `perl`, `ruby`, `node` (other interpreters)

## Key Findings

This demonstrates a **CRITICAL vulnerability**:
- ✗ Incomplete blocklist of dangerous commands
- ✗ Python can execute any arbitrary code
- ✗ Can bypass all security checks
- ✗ Achieves full reverse shell access

## Cleanup

After testing, you can remove the test directory:

```bash
rm -rf /tmp/test_output
```
