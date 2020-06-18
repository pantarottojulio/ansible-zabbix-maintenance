# Ansible Role: Zabbix

## O que esta role faz?

Cria um periodo de manutenção para uma lista de hosts apartir do horário de execução da playbook.

## Dependências

Para execução deste projeto é necessário o pacote python zabbix-api:

* Instalação da API do zabbix (https://pypi.org/project/zabbix-api/)
```
pip install zabbix-api
```

* Verificar se a API foi instalada
```
pip list | grep zabbix-api
```

* Importar zabbix_api no python
```
python

>> from zabbix_api import ZabbixAPI

exit()
```

* Verificar local de instalação da API
```
pip show zabbix-api
```
```
O location deve ser em ~/env/bin/python

Caso não esteja na location acima, copie os arquivos listados da location atual e cole em ~/env/bin/python/sites-packages/

Arquivos e pasta para copiar: 
- zabbix_api-0.5.4.dist-info
- zabbix_api.py
- zabbix_api.pyc
```
* Run the playbook `maintenance.yml`:
```
ansible-playbook -i 'localhost', --connection=local maintenance.yml --ask-vault-pass -vvvv -e 'ansible_python_interpreter=~/env/bin/python'
```
