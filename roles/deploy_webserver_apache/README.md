<!-- DOCSIBLE START -->

# 📃 Role overview

## deploy_webserver_apache



Description: Role para configurar e validar Apache com firewall


| Field                | Value           |
|--------------------- |-----------------|
| Readme update        | 05/06/2025 |











### Vars

**These are variables with higher priority**
#### File: vars/main.yml

| Var          | Type         | Value       |
|--------------|--------------|-------------|
| [apache_test_message](vars/main.yml#L3)   | str | `Test apache e automation` |    


### Tasks


#### File: tasks/main.yml

| Name | Module | Has Conditions | Comments |
| ---- | ------ | -------------- | -------- |
| latest Apache version installed | yum | False | Instala a versão mais recente do Apache |
| latest firewalld version installed | yum | False | Instala a versão mais recente do firewalld |
| firewalld enabled and running | service | False | Ativa e inicia o firewalld |
| firewalld permits http service | firewalld | False | Permite o serviço HTTP no firewalld |
| Ensure proper Apache configuration | copy | False | Copia a configuração customizada do ApacheCopia o logo para o site |
| Ensure proper Apache configuration | copy | False | Copia a configuração customizada do ApacheCopia o logo para o site |
| deploy index.html | template | False | Implanta o index.html a partir de template |
| Apache enabled and running | service | False | Inicia o serviço Apache |
| Test page link | uri | False | Verifica se a página inicial está acessível |
| Display result | debug | False | Exibe o código de status retornado pela URL |
| Fail if return code is not 200 | fail | True | Fails the play if return code is not 200 |
| Access page | debug | False | Exibe o link da página |




## Playbook

```yml
---
- name: Deploy webserver apache
  hosts: apache
  gather_facts: true
  roles:
    - role: ../roles/deploy_webserver_apache
```


## Author Information
Allan Roque

#### License

MIT

#### Minimum Ansible Version

2.9

#### Platforms

- **EL**: [8, 9]


#### Dependencies

No dependencies specified.
<!-- DOCSIBLE END -->
