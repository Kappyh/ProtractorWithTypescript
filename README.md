# ProtractorWithTypescript
Guia Básico para utilização do Protractor com Typescript para seguir os padrões do Angular 2


Protractor com Typescript

Protractor Configurações

Organização de diretórios

/tests
	/e2e
		/specs (Diretório de Specs)
		/PO ( Diretório de Page Objects e Arquivos de classes com construtores)
		protractor.conf.js ( main config file )


Configuração do Protractor.conf.js

O protractor deve ter um arquivo principal que irá executar todos os specs de teste do Jasmine, esse arquivo pode ter configurações como Framework utilizada, resolução de tela, sessões de navegador executadas em conjunto e etc.