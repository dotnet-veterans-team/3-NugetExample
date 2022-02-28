Bom dia pessoal tudo bom? 

A ideia dessa apresentação é demonstrar a utilização do Nuget como um facilitador no que tange a reutilização de códigos que são frequentemente utilizados em vários projetos, ou até mesmo as configurações padrões, configurações de aplicações (Rabit MQ, schedule de Apis), servidores SMTP de e-mails e afins..

Documentação utilizada como base:
https://docs.microsoft.com/pt-br/nuget/quickstart/create-and-publish-a-package-using-visual-studio?tabs=netcore-cli

Lembrete: a versão do dotnet do pacote afetara para quais versões da aplicação final aceitara o pacote nuget.

Links uteis:
https://www.nuget.org/


Segue alguns prints do processo realizado e ao fim o resultado.

•	Após criar seu usuário nuget você cria uma chave para seus pacotes.
 

•	Após finalizar as implementações você realiza um push para o nuget (bem similar ao git).
 

O pacote publicado está disponível para seu usuário podendo ser liberado para utilização da comunidade ou apenas para usuários desejados:

 

Neste pacote fiz apenas uma pequena demonstração de algo que sempre é desenvolvido e pode ser facilmente ser transformado em um pacote, validação de documentos e dados pessoais.

 

Comando para instalação: 
PM > Install-Package AlterSolutionsUtil -Version 1.0.0

Após a instalação você referencia na classe que irá utilizar:
using AlterSolutionsUtil.DocumentValidate.NIF;
using AlterSolutionsUtil.DocumentValidate.CPF;

e faz as validações necessárias:

bool isNif = NIFValidate.IsValid(request.Username);
bool isEmail = CPFValidate.IsValid(request.Username);

Aqui fiz uma simples demonstração de como utilizar “Validações” genéricas, porém, o potencial disso para melhorar a velocidade de desenvolvimento e ter de uma forma mais centralizada com métodos mais robustos e mais testados é grande (Na minha experiencia).

Obrigado a todos.

Atenciosamente.
