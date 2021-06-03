<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

## Passo a passo para criação do projeto

Os passos abaixo seguem os commits realizados no projeto, assumindo que você esteja no diretório C:\docker\.

1- Clonar o repositório do laradock  
```
C:\docker\> git clone https://github.com/laradock/laradock.git
```

2- Criar o arquivo de configuração ".env" do laradock
```
C:\docker\laradock> cp .env.example .env
```

3- Editar o arquivo .env para utilizar o php 7.4  
linha 42: PHP_VERSION=7.4

4- Criar o arquivo .conf para o projeto exemplo-laravel-vuejs-vuetify.conf

5- Alterar o arquivo hosts do Windows para encontrar o projeto exemplo-laravel-vuejs-vuetify.local
```
127.0.0.1    exemplo-laravel-vuejs-vuetify.local
```

6- Subir o ambiente
C:\docker\laradock> docker-compose up -d nginx

7- Entrar no container para executar os comandos laravel:
```
C:\docker\laradock> docker-compose exec workspace bash
```
* Para sair do container pressionar CTRL + D

8- Criar o projeto
```shell
/var/www# composer create-project laravel/laravel exemplo-laravel-vuejs-vuetify
```

9- No container, corrigir as permissões de acesso aos arquivos
```shell
/var/www# cd exemplo-laravel-vuejs-vuetify  
/var/www/exemplo-laravel-vuejs-vuetify# chmod -R guo+w ./storage
```

10- Subir o servidor e testar
/var/www/exemplo-laravel-vuejs-vuetify# php artisan serve
No navegador acessar o endereço http://exemplo-laravel-vuejs-vuetify.local

11- Instalar o laravel/ui no projeto
```shell
/var/www/exemplo-laravel-vuejs-vuetify# composer require laravel/ui
```

12- Configurar o vuejs no projeto
```shell
/var/www/exemplo-laravel-vuejs-vuetify# php artisan ui vue
```

13- Compilar os arquivos criados
```shell
/var/www/exemplo-laravel-vuejs-vuetify# npm install && npm run dev
```

14- Instalar o vuetify no projeto
```shell
/var/www/exemplo-laravel-vuejs-vuetify# npm install vuetify
```

15- Instalar a dependência sass-loader no projeto
```shell
/var/www/exemplo-laravel-vuejs-vuetify# npm install sass@~1.32 sass-loader deepmerge -D
```

16- Instalar o vuetify-loader no projeto
```shell
/var/www/exemplo-laravel-vuejs-vuetify# npm install vuetify-loader
```

17- Criar o arquivo de configurações resources/plugins/vuetify.js

18- Instalar o case-sensitive-paths-webpack-plugin no projeto
```shell
/var/www/exemplo-laravel-vuejs-vuetify# npm install --save-dev case-sensitive-paths-webpack-plugin
```

19- Configurar o vuetify-loader e o case-sensitive-paths-webpack-plugin no arquivo webpack.mix.js

20- Incluir o vuetify na aplicação no arquivo app.js

21- Corrigir importações do vuetify para nova versão nos arquivos vuetify.js e webpack.mix.js

22- Criar rota e arquivo php para testar vuetify

23- Verificando se o projeto continua executando corretamente e compilar os arquivos
```shell
/var/www/exemplo-laravel-vuejs-vuetify# npm run watch
```

24- Acessar o endereço http://exemplo-laravel-vuejs-vuetify.local/test
