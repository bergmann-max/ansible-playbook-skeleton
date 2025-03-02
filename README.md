# Ansible Playbook Skeleton

Dieses Repository enthält eine grundlegende Struktur für ein Ansible Playbook, das für die automatisierte
Serverkonfiguration und Verwaltung genutzt werden kann.

## Verzeichnisstruktur

```
ansible-project/
│── ansible.cfg          # Ansible Konfigurationsdatei
│── host.yml             # Inventory-Datei mit den Servern
│── site.yml             # Haupt-Playbook, das alle Rollen ausführt
│── requirements.yml     # Liste der benötigten Rollen und Collections
│── group_vars/          # Variablen für Host-Gruppen
│── host_vars/           # Variablen für einzelne Hosts
│── roles/               # Enthält alle Rollen für verschiedene Servertypen
│── README.md            # Diese Dokumentation
```

## Installation

1. **Ansible installieren:**
   ```sh
   sudo apt update && sudo apt install ansible -y
   ```
2. **Benötigte Rollen und Collections installieren:**
   ```sh
   ansible-galaxy install -r requirements.yml
   ansible-galaxy collection install -r requirements.yml
   ```

## Nutzung

Playbook für die gesamte Infrastruktur ausführen:
```sh
ansible-playbook site.yml --ask-become-pass
```

Falls `sudo` ohne Passwort genutzt wird:
```sh
ansible-playbook site.yml
```

## Anpassung
- **Inventory:** Server in `host.yml` eintragen.
- **Rollen:** Eigene Konfigurationen in `roles/` hinterlegen.
- **Variablen:** Anpassungen in `group_vars/` und `host_vars/` vornehmen.
