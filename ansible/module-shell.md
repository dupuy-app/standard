### Utilisation du module ansible.builtin.shell *`#SHE-1.0`*
#### Le module “ansible.builtin.shell” est utilisé de la manière suivante :

- Les paramètres utilisés sont exclusivement les suivants :
  - cmd
- Les paramètres listés précédemment sont toujours définis et sont écrits dans cet ordre



Par exemple :

```yaml
- name: launch of custom script
  ansible.builtin.shell:
    cmd: "/local/usr/custom_script.sh"
```

<br>
