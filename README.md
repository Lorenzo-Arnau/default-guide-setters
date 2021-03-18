### PUOI CERCARE CDN QUI

[JSDELIVER](https://www.jsdelivr.com/)

----------------------------------------------------------------------------------------------------------------------

### CDN Utilizzate in diversi progetti

[FONTAWESOME FREE v5.15.3](https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@5.15.3/css/all.css)
[JQUERY v3.6.0](https://cdn.jsdelivr.net/npm/jquery@3.6.0/dist/jquery.js)
[VUEJS v2.6.12](https://cdn.jsdelivr.net/npm/jquery@3.6.0/dist/jquery.js)
[BOOTSTRAP CSS v4.6.0](https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.css)
[AXIOS v0.21.1](https://cdn.jsdelivr.net/npm/axios@0.21.1/dist/axios.js)

----------------------------------------------------------------------------------------------------------------------

#### $\color{lightgreen}{\text{Da includere nell'head come nell'esempio qui sotto}}$

		<!DOCTYPE html>
		<html lang="it">
		<head>
			<meta charset="UTF-8">
			<meta http-equiv="X-UA-Compatible" content="IE=edge">
			<meta name="viewport" content="width=device-width, initial-scale=1.0">
			<!-- fontawesome -->
			<link rel="stylesheet" href=https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/all.min.css"/>
			<title></title>
		</head>
		<body>

----------------------------------------------------------------------------------------------------------------------

### NODEJS E NPM
[NODEJS](https://nodejs.org/en/download/)

		// da terminale
		node -v
		npm -v

----------------------------------------------------------------------------------------------------------------------

### LARAVEL E LARAVEL-MIX
[LARAVEL_MIX](https://laravel-mix.com/docs/6.0/installation)

		// da terminale
		npm init -y
		npm install laravel-mix --save-dev
		cd my-app
		touch webpack.mix.js

		// es. file webpack.mix.js
		let mix = require('laravel-mix');
		mix
			.sass('src/app.scss', 'dist/')
			.options({ processCssUrls: false })

		// da terminale per compilare scss
		npm mix

		// da terminale per compilare scss e "guardare" le modifiche in tempo reale
		npm mix watch

		/* se avete bisogno di aggiornare laravel-mix
		andate nel package.json e modificate la versione con quella che volete
		
		es.
		"devDependencies": {
			"laravel-mix": "^6.0.13"
		}

		dopodichè da terminale lasciate il comando npm install per installare/aggiornare le dipendenze */		

----------------------------------------------------------------------------------------------------------------------

### PATH CSS PER LARAVEL

		<html>
		<link rel="stylesheet" href="{{asset('css/app.css')}}">
		
----------------------------------------------------------------------------------------------------------------------

### INSTANZIAMENTO VUEJS

		new Vue({
			el: '#app',
			data:{

			},
			methods: {

			},
			mounted() {
				
			
			});
		Vue.config.devtools = true;

		/* per debug da console app.data o app.method()
		const app = new Vue({
			el: '#app',
		data: {
			message: 'Hello Vue!'
		},
		methods: {
			sayHello() {
				alert('Hello Vue!')
			}
		}
		});
		*/

----------------------------------------------------------------------------------------------------------------------

### LINK ICONA PAGINA

		<link rel="icon" href="IMG.png">

----------------------------------------------------------------------------------------------------------------------

### ISTRUZIONI PER PAGINA DI ERRORE MAMP

		cd C:\MAMP\logs\
		gc -Path php_error.log -Wait

----------------------------------------------------------------------------------------------------------------------

### SNIPPET VARDUMP MIGLIORE

		echo ‘<pre>’ . var_export($data, true) . ‘</pre>’; 

----------------------------------------------------------------------------------------------------------------------

### LISTA INIZIALIZZAZIONE LARAVEL CRUD
#### Crea nuovo progetto

		composer create-project --prefer-dist laravel/laravel:^7.0 MyProject

#### Per testare il database

		php artisan tinker
		DB::Connection()->getPdo()

#### Creiamo la migration per la nostra nuova tabella

		php artisan make:migration create_nome_table

#### Adesso in database/migrations troveremo un nuovo file.

#### Qui i dettagli sui vari tipi di colonne -> https://laravel.com/docs/7.x/migrations#creating-columns

#### Modifica la migration con le colonne necessarie e poi:

		php artisan migrate  

#### Per creare il model

		php artisan make:model NomeModello

#### Per creare il controller CRUD

		php artisan make:controller --resource NomeController

#### Installare Bootstrap.

		composer require laravel/ui:^2.4

		php artisan ui bootstrap
		npm install

----------------------------------------------------------------------------------------------------------------------

### INIZIALIZZARE COMPUTER A COMPOSER E LARAVEL
#### installare composer con .exe

		composer install
		composer update

creazione progetto laravel

		composer-create-project  --prefer-dist laravel/laravel:^7.0 nomeProgetto

andare su package.json
#### cambiare riga laravel mix con ^6.0.13

		npm install

----------------------------------------------------------------------------------------------------------------------

### CREARE UN CONTROLLER
		php artisan make:controller NomeController

		Route::get('controller','NomeController@metodo')

nel controller ricordarsi di creare funzione che ritorni una view

----------------------------------------------------------------------------------------------------------------------

### IMPOSTARE DATABASE

nel file .env sostituire il nome database e inserire utente e pswrd
verificare con

		php artisan tinker

in caso di problemi verificare il file php.ini nella cartella bin di Mamp


----------------------------------------------------------------------------------------------------------------------

### CREARE UN MODEL
		php artisan make:model NomeModello
ATTENZIONE: il model deve avere lo stesso nome del database al singolare così che laravel possa funzionare!

