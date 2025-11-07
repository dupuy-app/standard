### Espace entre les tasks *`#SPA-1.0`*
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
