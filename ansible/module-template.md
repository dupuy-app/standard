### Utilisation du module ansible.builtin.template *`#TEM-1.0`*
#### Le module “ansible.builtin.template” est utilisé de la manière suivante :

- Les paramètres utilisés sont exclusivement les suivants :
  - src
  - dest
  - backup
- Les paramètres listés précédemment sont toujours définis et sont écrits dans cet ordre
- La valeur du paramètre “backup” est toujours à “true”.
- Le fichier source indiqué dans le paramètre “src” est un fichier se trouvant dans le dossier “templates” du projet git
ou ses sous-dossiers.



Par exemple :

```yaml
- name: config file
  ansible.builtin.template:
    src: templates/deployment/parameters.conf.j2
    dest: /local/usr/parameters.conf
    backup: true
```

<br>
