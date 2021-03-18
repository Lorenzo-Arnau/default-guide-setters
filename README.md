## PATH CSS PER LARAVEL

        <html>
        <link rel="stylesheet" href="{{asset('css/app.css')}}">
-----------------------------------------------------------


## LINK FONTAWESOME
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" integrity="sha512-iBBXm8fW90+nuLcSKlbmrPcLa0OT92xO1BIsZ+ywDWZCvqsWgccV3gFoRBv0z+8dLJgyAHIhR35VZc2oM/gI1w==" crossorigin="anonymous" />

----------------------------------------------------------------------------------


## LINK JQUERY

        <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

----------------------------------------------------------------------------------


## LINK VUEJS

        <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>

----------------------------------------------------------------------------------

## LINK AXIOS

        <script src="https://cdnjs.cloudflare.com/ajax/libs/axios/0.20.0/axios.min.js"></script>

----------------------------------------------------------------------------------

## INSTANZIAMENTO VUE JS

new Vue({
 el: '#app',
 data:{

 },
});
Vue.config.devtools = true;

----------------------------------------------------------------------------------


## LINK ICONA PAGINA

        <link rel="icon" href="IMG.png">


---------------------------------------------------------------------------------


## ISTRUZIONI PER PAGINA DI ERRORE MAMP
        cd C:\MAMP\logs\
        gc -Path php_error.log -Wait

---------------------------------------------------------------------------------

## SNIPPET VARDUMP MIGLIORE

            echo ‘<pre>’ . var_export($data, true) . ‘</pre>’; 

---------------------------------------------------------------------------------


## LISTA INIZIALIZZAZIONE LARAVEL CRUD
### Crea nuovo progetto
         composer create-project --prefer-dist laravel/laravel:^7.0 MyProject

### Per testare il database
         php artisan tinker
         DB::Connection()->getPdo()

### Creiamo la migration per la nostra nuova tabella
         php artisan make:migration create_nome_table

### Adesso in database/migrations troveremo un nuovo file.

### Qui i dettagli sui vari tipi di colonne -> https://laravel.com/docs/7.x/migrations#creating-columns

### Modifica la migration con le colonne necessarie e poi:
         php artisan migrate  

### Per creare il model
         php artisan make:model NomeModello

### Per creare il controller CRUD
         php artisan make:controller --resource NomeController

### Installare Bootstrap.
         composer require laravel/ui:^2.4

         php artisan ui bootstrap
         npm install

---------------------------------------------------------------------------------
## INIZIALIZZARE PROGETTO SOLO SCSS
         nmp init -y
         npm install laravel-mix --save-dev
         npx mix
#### creare cartelle e modificare webpack.mix.js


---------------------------------------------------------------------------------
## INIZIALIZZARE COMPUTER A COMPOSER E LARAVEL
### installare composer con .exe
         composer install
         composer update

creazione progetto laravel

         composer-create-project  --prefer-dist laravel/laravel:^7.0 nomeProgetto

andare su package.json
#### cambiare riga laravel mix con ^6.0.13
        npm install

---------------------------------------------------------------------------------
## CREARE UN CONTROLLER
         php artisan make:controller NomeController

         Route::get('controller','NomeController@metodo')

nel controller ricordarsi di creare funzione che ritorni una view

----------------------------------------------------------------------------------
## IMPOSTARE DATABASE

nel file .env sostituire il nome database e inserire utente e pswrd
verificare con

         php artisan tinker

in caso di problemi verificare il file php.ini nella cartella bin di Mamp


---------------------------------------------------------------------------


## CREARE UN MODEL
         php artisan make:model NomeModello
ATTENZIONE: il model deve avere lo stesso nome del database al singolare così che laravel possa funzionare!

