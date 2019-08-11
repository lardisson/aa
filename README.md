# Parte 1

###Utilização
Para executar o deploy do app basta criar um arquivo criptografado com o comando abaixo:
```
 ansible-vault  create inventories/aws/group_vars/all/vault.yml 
```
Conteúdo do arquivo vault.yml
```
---
aws_access_key: "xxxxxx"
aws_secret_key: "xxxxxxx"
app_token: "xxxxx"
```  
Após isso basta execultar  o playpook com mostra abaixo:
```
ansible-playbook test_geru.yml -i inventories/aws/ --ask-vault
```
# Parte 2
O cenário representan no diagrama da parte 2 do teste  esta representando um sitem que utiliza  Cloudfront como camada de segurança para mitigras os ataques de DDOS, S3 para armazenamento de todo o conteúdo estáticos do site e API Gatway como triguer do lambda que por sua vez  é execultado e cobrado apenas pela utilização sem nenhuma administração de servicoderes  e por fim DynamoDB como base de dados para  dados dinamicos.
