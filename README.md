# ProtractorWithTypescript
Guia Básico para utilização do Protractor com Typescript para seguir os padrões do Angular 2

 - **Em construção**


Instalações:

- [NodeJS superior a versão v.0.10.0](https://nodejs.org/en/)
- Jasmine
    ```
    npm install --save-dev jasmine
    
    ```
- Protractor 
- Atualização do Webdriver-Manager
- [Jasmine HTML Reporter ](https://www.npmjs.com/package/protractor-jasmine2-html-reporter)
- Typescript
    Instalando typescript globalmente
    
    ```
    npm install -g typescript
    
    ```


## Protractor Config com Typescript

Protractor Configurações

Organização de diretórios

- tests
	- e2e
		- specs (Diretório de Specs)
		- PO ( Diretório de Page Objects e Arquivos de classes com construtores)
		- protractor.conf.js ( main config file )


**Configuração do Protractor.conf.ts**

O protractor deve ter um arquivo principal que irá executar todos os specs de teste do Jasmine, esse arquivo pode ter configurações como Framework utilizada, resolução de tela, sessões de navegador executadas em conjunto e etc.



Configuração padrão

```
//protractor.conf.ts

import 'jasmine';   // Importa Framework Jasmine
import { Config } from 'protractor';  // Importação do Config do Protractor

export let config: Config = {

  framework: 'jasmine',  // Declara o uso do Jasmine
  seleniumAddress: 'http://localhost:4444/wd/hub',    // Declara a URL do Selenium
  noGlobals: true,    // Remove conflito com Jquery
  specs: ['specs/**spec.js'], // Caminho do(s) arquivo(s) spec
  baseUrl: 'http://localhost:8080', // URL base da aplicação

  capabilities: {
    browserName: 'chrome'   // Informa o navegador que irá rodar o teste
  }
}

```


**Configuração com multicapabilities & responsive browser**


```
// protractor.conf.js

import 'jasmine';
import { Config } from 'protractor';

export let config: Config = {

  framework: 'jasmine',
  seleniumAddress: 'http://localhost:4444/wd/hub',
  noGlobals: true,
  specs: ['specs/**spec.js'],
  baseUrl: 'http://localhost:8080',
  maxSessions: 1, // Limitação de execução simultanea de testes no capabilities

  multiCapabilities: [{
    browserName: 'chrome'
  }, {
    browserName: 'chrome',
    chromeOptions: {
      mobileEmulation:{
        deviceName: 'Google Nexus 5'    // Irá emular a resolução desse dispositivo 
      }
    }
  }]
}

```








