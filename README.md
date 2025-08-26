# Wazuh Brute-force Lab

## Cel
Testowałem własną regułę Wazuh, która wykrywa 5 nieudanych logowań Windows (EventID 4625) w ciągu 60 sekund.

## Co jest w repo
- `local_rules.xml` — reguła korelacyjna.
- `screenshots/` — dowód działania reguły.

## Jak to działa
1. Wgrać `local_rules.xml` do `/var/ossec/etc/rules/`.
2. Zrestartować Wazuh Manager: `sudo systemctl restart wazuh-manager`.
3. Wygenerować 5 błędnych logowań na Windows (EventID 4625).
4. Sprawdzić alert w `/var/ossec/logs/alerts.log` (Rule 100010).
