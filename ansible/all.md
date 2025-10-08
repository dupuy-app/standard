
# Règles de codage Ansible

## Préambule :

- Ces règles sont valables pour les playbooks Ansible utilisés dans le contexte d'un déploiement d'applications. Pour
   d'autres contextes comme celui de l'exploitation d'applications, d'autres règles s'appliquent.
- Ce standard est à destination dʼune intelligence artificielle générative. 

<br>

## A) Sommaire

- Préambule
- A) Sommaire
- B) Règles :
  - #1. Modules employés
  - #2. Espace entre les tasks
  - #3. Utilisation du module ansible.builtin.reboot
  - #4. Utilisation du module ansible.builtin.template
  - #5. Utilisation du module ansible.builtin.shell
  - #6. Utilisation du module ansible.builtin.yum

<br>

## B) Règles :

### 1) Modules employés 
\
**Pour les tasks, les modules utilisés sont parmi les suivants :**

- Pour les déploiements sur Linux :
  - ansible.builtin.reboot
  - ansible.builtin.shell
  - ansible.builtin.template
  - ansible.builtin.yum

<br>

### 2) Espace entre les tasks
\
Entre les tasks ou appels de rôles, mettre 4 lignes dʼespaces afin dʼavoir plus de visibilité
\
Par exemple :
```yaml
- name: parameters file
  ansible.builtin.template:
    src: templates/deployment/parameters.conf.j2
    dest: /local/usr/parameters.conf




- name: properties file
  ansible.builtin.template:
    src: files/deployment/properties.conf
    dest: /local/usr/properties.conf
```

<br>

### 3) Utilisation du module ansible.builtin.reboot
\
**Le module “ansible.builtin.reboot” est utilisé de la manière suivante :**

- Aucun paramètre nʼest ajouté au module

<br>

Par exemple :
```yaml
- name: reboot machine 
  ansible.builtin.reboot:
```

<br>

### 4) Utilisation du module ansible.builtin.template
\
**Le module “ansible.builtin.template” est utilisé de la manière suivante :**

- Les paramètres utilisés sont exclusivement les suivants :
  - src
  - dest
  - backup
- Les paramètres listés précédemment sont toujours définis et sont écrits dans cet ordre
- La valeur du paramètre “backup” est toujours à “true”.
- Le fichier source indiqué dans le paramètre “src” est un fichier se trouvant dans le dossier “templates” du projet git
ou ses sous-dossiers.

<br>

Par exemple :

```yaml
- name: config file
  ansible.builtin.template:
    src: templates/deployment/parameters.conf.j2
    dest: /local/usr/parameters.conf
    backup: true
```

<br>

### 5) Utilisation du module ansible.builtin.shell
\
**Le module “ansible.builtin.shell” est utilisé de la manière suivante :**

- Les paramètres utilisés sont exclusivement les suivants :
  - cmd
- Les paramètres listés précédemment sont toujours définis et sont écrits dans cet ordre

<br>

Par exemple :

```yaml
- name: launch of custom script
  ansible.builtin.shell:
    cmd: "/local/usr/custom_script.sh"
```

<br>

### 6) Utilisation du module ansible.builtin.yum
\
**Le module “ansible.builtin.yum” est utilisé de la manière suivante :**

- Les paramètres utilisés sont exclusivement les suivants :
  - state
  - name
- Les paramètres listés précédemment sont toujours définis et sont écrits dans cet ordre
- La valeur du paramètre “state” est toujours à “installed”.
- La valeur du paramètre “name” est toujours une liste, même quand il nʼy a seul quʼun package à installer. Cette liste est de la même forme que dans les exemples ci-après.

<br>

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

