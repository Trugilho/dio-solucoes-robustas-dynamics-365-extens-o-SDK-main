# Formação CRM Dynamics 365 Desafio2 Criando Soluções Robustas no Dynamics 365 com a Extensão SDK

O projeto prático "Criando Soluções Robustas no Dynamics 365 com a Extensão SDK" tem como objetivo explorar a funcionalidade e capacidade do Dynamics 365 utilizando a Extensão SDK.

Para o projeto, é necessário a instalação do Visual Studio,  utilizando a extensão SDK do Microsoft Dynamics Costumer 365 Engagement, e também a ferramenta de apoio XrmToolBox para criar uma solução que atenda às necessidades do projeto especificadas em vídeos.

O projeto pode incluir a criação de fluxos de trabalho personalizados, criação de plug-ins, personalização da interface do usuário e desenvolvimento de processos de negócios personalizados.

Para garantir a eficiência da solução criada, é importante seguir todas as etapas do processo de desenvolvimento e implantação, como a criação de Plugins, Actions e  Workflow Assembly.

## Roberto Trugilho Moreira<br>Em desenvolvimento...

# Comece a usar o Saint Systems Microsoft Dynamics 365 SDK para PHP

_This SDK is currently in preview. Please continue to provide [feedback](https://github.com/saintsystems/dynamics-sdk-php/issues/new) as we iterate towards a production-supported library._

[![Build Status](https://travis-ci.org/saintsystems/dynamics-sdk-php.svg?branch=master)](https://travis-ci.org/saintsystems/dynamics-sdk-php)

For WordPress users, please see our [Gravity Forms Dynamics 365 Add-On](https://www.saintsystems.com/products/gravity-forms-dynamics-crm-add-on/).

## Instale o SDK

Você pode instalar o PHP SDK com o Composer.

```
{
    "require": {
        "Microsoft/Dynamics": "0.1.*"
    }
}
```

## Introdução ao Microsoft Dynamics 365

### Registre seu aplicativo

Registre seu aplicativo para usar a API do Microsoft Dynamics 365 usando um dos seguintes
portais de autenticação suportados:

- [Microsoft Azure Active Directory](https://manage.windowsazure.com): Registro
  um novo aplicativo no Active Directory do seu locatário para dar suporte ao trabalho ou à escola
  usuários para seu locatário ou vários locatários.
- [Microsoft Application Registration Portal](https://apps.dev.microsoft.com) (**Coming Soon**):
  Registre um novo aplicativo que seja autenticado usando o terminal de autenticação v2.0. Este ponto de extremidade autentica contas pessoais (Microsoft) e corporativas ou escolares (Azure Active Directory).

### Autenticar com o serviço Microsoft Graph

O SDK do Microsoft Dynamics 365 para PHP não inclui nenhuma implementação de autenticação padrão.
Em vez disso, você pode autenticar com a biblioteca de sua escolha.

Ao autenticar, basta solicitar acesso à URL da instância do Dynamics 365 usando o parâmetro `resource` do Azure AD.

### Ligue para o Microsoft Dynamics 365

Veja a seguir um exemplo que mostra como chamar a API da Web do Microsoft Dynamics 365.

```php
use Microsoft\Dynamics\Dynamics;
use Microsoft\Dynamics\Model;

class UsageExample
{
    $instanceUrl = 'https://contoso.crm.dynamics.com';
    $accessToken = 'xxx';

    $dynamics = new Dynamics();
    $dynamics->setInstanceUrl($instanceUrl)
             ->setAccessToken($accessToken);

    $leads = $dynamics->createRequest("GET", "/leads")
                  ->setReturnType(Model\Lead::class)
                  ->execute();

    $lead = $leads[0];

    echo "Hello, I am $lead->getFirstName() ";

    // OR GET a specific lead by ID

    $lead = $dynamics->createRequest("GET", "/leads(xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx)")
                  ->setReturnType(Model\Lead::class)
                  ->execute();

    echo "Hello, I am $lead->getFirstName() ";
}
```

### Executar testes

Run `vendor/bin/phpunit` from the base directory.

## Documentação e recursos

- [Documentation](https://github.com/saintsystems/dynamics-sdk-php/blob/master/docs/index.html)

- [Wiki](https://github.com/saintsystems/dynamics-sdk-php/wiki)

- [Examples](https://github.com/saintsystems/dynamics-sdk-php/wiki/Example-calls)

- [Microsoft Dynamics 365 website](https://www.microsoft.com/en-us/dynamics365)

- [Microsoft Dynamics 365 Web API Documentation](https://msdn.microsoft.com/library/mt593051.aspx#documentation)

## Problemas

Visualize ou registre problemas no [Issues](https://github.com/saintsystems/dynamics-sdk-php/issues) guia no repositório.

## Direitos autorais e licença

Copyright (c) Saint Systems, LLC. All Rights Reserved. Licensed under the MIT [license](LICENSE).
