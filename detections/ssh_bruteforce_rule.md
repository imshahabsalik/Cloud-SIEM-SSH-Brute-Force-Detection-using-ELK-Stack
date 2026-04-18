# SSH Brute Force Detection Rule

## Query

event.code:4625 and (process.name:sshd or winlog.event_data.LogonProcessName:ssh)

## Condition

* Count ≥ 10
* Time window: 1 minute

## Description

Detects multiple failed SSH login attempts indicating potential brute-force activity.

## MITRE ATT&CK Mapping

* T1110: Brute Force
