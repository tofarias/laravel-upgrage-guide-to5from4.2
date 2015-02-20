# laravel-upgrage-guide-to5from4.2

Conteúdo original: [Upgrading To 5.0 From 4.2](http://laravel.com/docs/master/upgrade#upgrade-5.0/ "Upgrading To 5.0 From 4.2")

# Atualizando da versão 4.2 para a versão 5

## Nova instalação, em seguida, migrar

O método recomentado para fazer a atualização é criar uma nova instação laravel 5 e então copiar seus arquivos exclusivos do projeto que está na versão 4.2 para a nova instação do laravel 5.
Isso inclui *controllers*, *rotas*, *models do Eloquent*, *comandos do Artisan*, *assets*, e outro código específico do seu projeto.
Para iniciar, instale uma nova aplicação Larave 5 em novo diretório no seu ambiente local. Nós vamos discutir cada parte do processo de migração no futuro com mais detalhes.

## Pacotes e Dependências do Composer

Não esqueça de copiar qualquer dependência adicional do composer para o seu novo projeto da versão 5. Iso inclui pacotes de terceiros como SDKs.
Alguns pacotes do laravel podem não ser compativeis coma versão 5 ou com a *release* inicial. Verifique com o mantenedor dos pacotes para determinar a versão adequada do pacote para usar no Laravel 5. Uma vez adicionado qualquer dependência do *composer* você precisa executar o comando *composer update*.

## Namespacing

Por padrão, o projeto Laravel 4 não utiliza *namespacing* dentro do código da sua aplicação. Então, por exemplo, todas as *models* do *Eloquent* e *controllers* simplesmente pertencem ao *namespace* global. Para uma rápida migração, você pode simplesmente deixar essas classes no *namespace* global no Laravel 5.

## Configuração

### Migrando Variáveis de Ambiente

Copie e renomeie o novo arquivo **.env.example** para **.env**, que é equivalente a versão 5.0 do antigo **.env.php**. Defina valores de propriedades nele, como o seu **APP_ENV e APP_KEY (sua chave criptografada)**, suas credenciais do banco de dados, o *cache* e driver de sessão.

Você ainda pode, copiar qualquer valor que você tinha no antigo arquivo **.env.php** e aplicar em ambos arquivos **.env** *(o real valor para seu ambiente local)* e **.env.example** *(valores que servirão de instrução simples para cada membro da equipe)*

Para maiores informações sobre configuração de ambiente, veja a documentação completa.

**ATENÇÃO: você precisa colocar o arquivo .env no seu servidor de produção antes de fazer o deploy do seu projeto Laravel 5.**



### CacheManager
Se na sua aplicação foi injetado **Illuminate\Cache\CacheManager** para obter uma versão não *Facade* do Laravel cache, use **inject Illuminate\Contracts\Cache\Repository**.

### Paginação
Substitua todas as chamadas de **$paginator->links()** para **$paginator->render()**.

### Beanstalk Queuing
Laravel 5 agora precisa do **"pda/pheanstalk": "~3.0"** ao invés de **"pda/pheanstalk": "~2.1"**.

### Remote
Desabilidato.

### Workbench

Desabilidato.
