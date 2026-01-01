## Findings & Analysis

Analysis of the authentication logs revealed multiple failed SSH login attempts
targeting the user account **admin** from a single external IP address.

The repeated failures over a short time window indicate a **brute-force
authentication attempt**. Shortly after the failed attempts, a successful
login was observed for a legitimate user account, suggesting continued probing
of the SSH service.

This pattern is commonly associated with automated attack tools attempting to
guess credentials.

## Indicators of Compromise (IoCs)

- Source IP: `192.168.1.50`
- Targeted username: `admin`
- Service targeted: SSH (port 22)
- Attack type: SSH brute-force / credential guessing

- ## Alert Summary

Multiple failed SSH login attempts were detected from a single IP address
attempting to authenticate as the `admin` user within a short time window.
This activity triggered a brute-force alert based on repeated authentication
failures followed by a successful login.

## SOC Response Actions

- Identified the attacking IP address from authentication logs
- Reviewed successful login to confirm whether access was authorized
- Recommended blocking the source IP using firewall rules
- Suggested disabling direct SSH login for privileged accounts
- Advised enforcing key-based SSH authentication

- ## Conclusion

This investigation demonstrates how SSH brute-force attacks can be identified
through Linux authentication logs. By analyzing failed and successful login
patterns, defenders can detect suspicious activity early and respond before
systems are compromised.

This project reflects real-world SOC workflows including log review,
alert triage, and incident documentation.
