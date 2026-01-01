# Investigation Notes – SSH Authentication Analysis

## Log Source
- File: logs/auth.log
- Environment: Kali Linux (simulated training logs)

## Timeline Summary
- Repeated failed SSH login attempts for invalid user "admin"
- Source IP: 192.168.1.50
- Multiple attempts within short time window
- One successful login for legitimate user "kali" from internal IP 192.168.1.25

## Threat Assessment
- Activity consistent with SSH brute-force or credential enumeration
- Targeting default/admin accounts
- No evidence of successful compromise from attacker IP

## Severity
- Medium

## Recommended Mitigations
- Block IP 192.168.1.50
- Disable password-based SSH authentication
- Enforce SSH key authentication
- Implement fail2ban or equivalent protection
