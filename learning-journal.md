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


## Exercise: SSH Service Health Investigation

### Objective
Investigate the health of the SSH service on my Raspberry Pi.

### Tools
- systemctl
- journalctl

### Investigation
Checked the current SSH service status using
`systemctl status ssh --no-pager`.

Reviewed the 10 most recent SSH service log entries
using `sudo journalctl -u ssh -n 10 --no-pager`.

### Findings
The SSH service started successfully, as indicated
by the "Started ssh.service" message.

The logs showed that the SSH server was listening
for incoming connections.

Multiple successful SSH password authentications
and session openings were recorded.

These entries are consistent with my remote
connections from my Windows laptop to the
Raspberry Pi.

No errors or failed authentication attempts
appeared in the log entries reviewed.

However, this does not guarantee that no other
connection attempts occurred outside the
displayed entries.

### Verification
Used `systemctl status ssh --no-pager` to verify
that the SSH service was active (running).

Reviewed recent SSH logs using
`sudo journalctl -u ssh -n 10 --no-pager`.

The logs showed successful authentication
and session-opening events.

Together with my successful remote SSH connection,
these observations indicate that the SSH service
was functioning correctly at the time of
the investigation.

### Security Considerations
Used read-only diagnostic commands.

Did not interrupt or restart the running SSH service.

Excluded private IP addresses, usernames, and
other sensitive information from documentation.

Recognized that successful password authentication
does not automatically guarantee system security.

### Conclusion
The SSH service was operating correctly during
the investigation.

The service was running, accepting authenticated
connections, and allowing remote administration
of the Raspberry Pi.

No immediate service issues were identified
in the logs reviewed.
