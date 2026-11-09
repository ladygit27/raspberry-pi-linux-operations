# Linux Operations Learning Journal

## Exercise: File Permission Investigation

### Problem
A simulated configuration file with sensitive information
had permissions of 644,
allowing its owner to read and write, and group and
other users to read.

### Investigation
Used `ls -l` and `stat` to inspect file permissions.

### Remediation
Changed permissions from 644 to 600 using `chmod`.

### Verification
Confirmed that only the file owner had read and
write permission.

### Security Principle
Least privilege: users should receive only the
access required for their tasks.
