### 6) Utilisation du module ansible.builtin.yum
#### Le module “ansible.builtin.yum” est utilisé de la manière suivante :

- Les paramètres utilisés sont exclusivement les suivants :
  - state
  - name
- Les paramètres listés précédemment sont toujours définis et sont écrits dans cet ordre
- La valeur du paramètre “state” est toujours à “installed”.
- La valeur du paramètre “name” est toujours une liste, même quand il nʼy a seul quʼun package à installer. Cette liste est de la même forme que dans les exemples ci-après.



Par exemple :
```yaml
- name: install libXau
  ansible.builtin.yum:
    state: installed
    name:
    - libXau




- name: install libXext & libXmu
  ansible.builtin.yum:
    state: installed
    name:
    - libXext
    - libXmu
```

<br>
