### Considerações para o  uso da ferramenta:
  A ferramenta utilizada foi em base a linguagem javasript que a empresa em que estou atuando utiliza no back-end e front-end (empresa com grupo pequeno de 
desenvolvedores e um unico QA.. eu, prazer), tendo a princial sugestão em caso o Qa fique ausente o time de desenvolvimento possa atuar nos teste de integração
por isso que busquei a ferrmenta postman;

Caso seu contexto seja diferente poderá outras abordagem paa teste automatizado a nivel de inteegração como pactumJs, Cypress ou Robotframework

### Pontos positivos: 
1. Então quando se fala em "teste em api" a maioria dos devs utilizam o postman para manipulação;
2. O postman utiliza o a linguaguem javascript para criar scipts de testes;
3. Newman para gerar relatórios;
4. Ajuda o time de desenvolvimento a ter testes relativamente com baixa complexidade de manutenção e de facil compresão;
5.  Ter testes regressisvos a nivel de integração, (é necessário que você saiba testar antes de automatizar testes);

### Pontos negativos:
1. Postman tem um problema de insegurança (em algumas empresa o insominia e uma opção utilizada)
2. Dev podem não querer utilizar mais uma ferramenta
3. Incopatibilidade em Apis que não utilizem a arquitetura Rest

---

### Pré requisitos: 

- [node.js 20.x](https://nodejs.org/en/download/package-manager)
- [newman](https://www.npmjs.com/package/newman) 
- [newman-reporter-htmlextra](https://www.npmjs.com/package/newman-reporter-htmlextra)
- [fork-e- clone_do_projeto]()

---


### Passos

1. Abrir Postman
2. Importar Cada Collection
3. Importar Workspace e Enviroment
4. Abra o terminal dentro da pasta do projeto

 - **Exemplo C:\meus-projetos\postman-cli-test** 


```
newman run 01_usuarios.postman_collection.json -e develop.postman_environment.json -g workspace.postman_globals.json -r cli,junit,json,htmlextra --reporter-junit-export junitReport1.xml --reporter-htmlextra-export tests_users.html
newman run 02_login.postman_collection.json -e develop.postman_environment.json -g workspace.postman_globals.json --delay-request 1 -r cli,junit,json,htmlextra --reporter-junit-export junitReport2.xml --reporter-htmlextra-export tests_login.html
```

5. Abir arquivos gerados 'tests_users.html' e 'tests_login.html' dentro da pasta do projeto.
