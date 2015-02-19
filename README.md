# laravel-upgrage-guide-to5from4.2

Conteúdo original: [Upgrading To 5.0 From 4.2](http://laravel.com/docs/master/upgrade#upgrade-5.0/ "Upgrading To 5.0 From 4.2")

# Atualizando da versão 4.2 para a versão 5

## Nova instalação, em seguida, migrar

O método recomentado para fazer a atualização é criar uma nova instação laravel 5 e então copiar seus arquivos exclusivos do projeto que está na versão 4.2 para a nova instação do laravel 5.
Isso inclui *controllers*, *rotas*, *models do Eloquent*, *comandos do Artisan*, *assets*, e outro código expecífico do seu projeto.
Para iniciar, instale uma nova aplicação Larave 5 em novo diretório no seu ambiente local. Nós vamos discutir cada parte do processo de migração no futuro com mais detalhes.
