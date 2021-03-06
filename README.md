<!-- ✨ Magic ✨ -->

### Puoi cercare CDN qui

- [JSDELIVER](https://www.jsdelivr.com/)  

---

### DA INCLUDERE NELL'HEAD PER QUANDO SI FA IL RESPONSIVE

```sh
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### CDN Utilizzate in diversi progetti

- [FONTAWESOME FREE](https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@5.15.3/css/all.css) - v5.15.3  
- [JQUERY](https://cdn.jsdelivr.net/npm/jquery@3.6.0/dist/jquery.js) - v3.6.0   
- [VUE.JS](https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js) - v2.6.12  
- [BOOTSTRAP CSS](https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.css) - v4.6.0
- [AXIOS](https://cdn.jsdelivr.net/npm/axios@0.21.1/dist/axios.js) - v0.21.1

> Da includere nell'head come nell'esempio

```sh
    <!DOCTYPE html>
    <html lang="it">
    <head>
      <!-- fontawesome -->
      <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@5.15.3/css/all.css"/>
    </head>
```

---


### FILTRARE I DATI - versione lunga e corta
>Passiamo l'indice al metodo show del Controller CRUD   
La Classe (Model) troverà il record della tabella con id uguale a quello passato al metodo show() e lo restituirà alla view

```sh
    // versione lunga - long version
    public function show($id)
    {
      // 
      $var = Model::find($id);
      return view('nome-della-rotta', ['path-della-view' => $var]));
    }
     
    // versione corta - short version
    public function show(Model $id)
    {
        return view("nome-della-rotta", compact('id'));
    }
```
`ATTENZIONE` : Da terminale controllare le rotte

```sh
    php artisan route:list
```

---

### Node.js e npm

- [NODE.JS](https://nodejs.org/en/download/)  

>Con l'installazione di Node verrà installato anche il package manager   
Per verificare le versioni presenti sul pc lanciare i seguenti comandi

```sh
    node -v
    npm -v
```

---

### Doctrine

Per usare l'update nelle migrations:


        "doctrine/dbal": "^2.0"


aggiungetelo  al **composer.json** e poi lanciate


        composer install


qui più informazioni https://stackoverflow.com/questions/33817983/artisan-migration-error-class-doctrine-dbal-driver-pdomysql-driver-not-fo


---

### LARAVEL E LARAVEL-MIX

- [LARAVEL_MIX](https://laravel-mix.com/docs/6.0/installation)  

>Inizializzare il progetto creando il package.json 
```sh
    npm init -y
```    


>Installare laravel-mix
```sh    
    npm install laravel-mix --save-dev        
```

>Spostarsi nel progetto (la cartella) e creare il file webpack.mix.js
```sh    
    cd my-app
    touch webpack.mix.js    
```

>es. file webpack.mix.js
```sh    
    let mix = require('laravel-mix');
    mix
      .sass('src/app.scss', 'dist/')
      .options({ processCssUrls: false })
```

>Da terminale per compilare scss
```sh    
    npx mix
```

>Da terminale per compilare scss e "guardare" le modifiche in tempo reale
```sh    
    npm mix watch
```

>Per aggiornare laravel-mix andare nel package.json
e modificare la versione come nell'esempio
```sh    
    "devDependencies": {
      "laravel-mix": "^6.0.13"
    }
```
>dopodichè da terminale per installare/aggiornare le dipendenze
```sh
    npm install
```

---

### NPM FONTAWESOME E IMPORT SU APP.SCSS

npm install --save-dev @fortawesome/fontawesome-free

>copiare questo all'interno di app.scss
@import '~@fortawesome/fontawesome-free/css/all.min.css';

### PATH CSS & JS PER LARAVEL

		
		<link rel="stylesheet" href="{{asset('css/app.css')}}">
		
		<script src="{{ asset('js/app.js') }}"></script> (edited) 

#### LINK DOCUMENTAZIONE FILL/FILLABLE

  https://laravel.com/docs/7.x/eloquent#mass-assignment


#### LINK SULLA VALIDAZIONE DEI CAMPI DEL FORM IN LARAVEL 

https://laravel.com/docs/7.x/validation

https://laravel.com/docs/7.x/validation#available-validation-rules
		
---

### INSTANZIAMENTO VUEJS

>script.js
```sh
    new Vue({
      el: '#app',
      data:{

      },
      methods: {

      },
      mounted() {
        
      }
    });
    Vue.config.devtools = true;
```
>Per debug da console app.data o app.method()
```sh
    const app = new Vue({
      el: '#app',
      data: {
        message: 'Hello Vue!'
      },
      methods: {
        sayHello() {
          alert('Hello Vue!')
        }
      },
      mounted() {
        
      }
    });
    Vue.config.devtools = true;
```

---

### LINK ICONA PAGINA

		<link rel="icon" href="IMG.png">

---

### ISTRUZIONI PER PAGINA DI ERRORE MAMP

		cd C:\MAMP\logs\
		gc -Path php_error.log -Wait

---

### SNIPPET VARDUMP MIGLIORE

		echo ‘<pre>’ . var_export($data, true) . ‘</pre>’; 

---

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

---

#### Installare Bootstrap Auth.

composer require laravel/ui:2.4 //se nn già fatto prima
php artisan ui bootstrap --auth // attenzione: ricrea il file app.scss (
quindi cancella gli import aggiuntivi come font awesome e partials) -> fallo all’inizio, dopo bootstrap
npm install
php artisan migrate // per lanciare la migratiom creata automaticamente

---

### INIZIALIZZARE COMPUTER A COMPOSER E LARAVEL
#### installare composer con .exe

		composer install
		composer update

creazione progetto laravel

		composer-create-project  --prefer-dist laravel/laravel:^7.0 nomeProgetto

andare su package.json
#### cambiare riga laravel mix con ^6.0.13

		npm install

---

### CREARE UN CONTROLLER
		php artisan make:controller NomeController

		Route::get('controller','NomeController@metodo')

nel controller ricordarsi di creare funzione che ritorni una view

---

### IMPOSTARE DATABASE

nel file .env sostituire il nome database e inserire utente e pswrd
verificare con

		php artisan tinker

in caso di problemi verificare il file php.ini nella cartella bin di Mamp


---

### CREARE UN MODEL
		php artisan make:model NomeModello
ATTENZIONE: il model deve avere lo stesso nome del database al singolare così che laravel possa funzionare!


---


### INSTALLAZIONE BOOTSTRAP FRAMEWORK IN LARAVEL

**NB prima di procedere all'installazione di Bootstrap, assicurarsi di aver inizializzato laravel-mix**

1. Per installare Bootstrap nel nostro progetto laravel, bisogna puntare da terminale alla repo-progetto nella quale ci interessa installare Bootstrap e lanciare il comando:


   		 composer require laravel/ui:^2.4



2. terminata l'installazione dei pacchetti eseguire il comando


    	php artisan ui bootstrap




questo comando aggiorna le dipendenze del nostro file package.json aggiungendo appunto la dipendenza di bootstrap.

3. il terminale ci chiederà di eseguire il comando 



   		 npm install



questo comando eseguirà un download dei webpack aggiornati della nostra nuova dipendenza bootstrap
fatto questo eseguire eventuali comandi richiesti dal terminale.


---


### CAMBIARE INDENTAZIONE EXPLORER FILE TREE VScode


#### File -> Preferences -> Settings -> 
sulla barra **'search settings'** scrivere **"tree"** (senza apici) poi sotto
#### User -> Workbench 
e sotto **Workbench** click su **Appearance** quindi aumentare il valore sotto a **'Controls tree indentation in pixels.'** e premere INVIO.

---
## CREARE UN NUOVO ITEM IN DATABASE

1. Nel metodo **create** definire la view dove si trova il **form** con un semplice **return** che ritorni la view.

2. #### alla creazione del form sono indispensabili queste cose:


		 <form action="{{route('oggetto.store')}}" method="post">
         @csrf
         @method('POST')

il **@csfr** è un sistema di verifica di Laravel aggiuntivo.

il **@method('POST')** serve per indicare a Laravel quale metodo utilizzeremo(POST,DELETE ecc ecc)

per vedere cosa abbiamo passato nel form bisogna andare in

		network->nome(post)->headers->form data

**ATTENZIONE** il valore name="" di ciascun input deve essere uguale a quelli che passiamo nella variabile **$fillable** nel **Metodo**( punto 3 )		

3. Nella sezione Store mettiamo in variabile i dati inviati dal form

		$data=$request->all();

   Inizializziamo un nuovo oggetto

		$oggetto=new Oggetto();

	Andiamo a completare il Metodo aggiungendo la variabile fillable con i campi del nostro database

		protected $fillable=['param1','param2','param3','param4']

	tornaimo nella sezione **store** e aggiungiamo

			$oggetto->fill($data)
			$oggetto->save()

	al salvataggio ritorniamo l'ultimo oggetto creato ,mostrato nel metodo **show**

			$oggettoStored=Oggetto::orderBy('id','desc')->first();
			return redirect()->route('oggetto.show',$oggettoStored)		
---

## VALIDATION DI BOOTSTRAP (PER CAMPI OBBLIGATORI)


[DOCUMENTAZIONE VALIDATE BOOTSTRAP](https://getbootstrap.com/docs/4.0/components/forms/)

#### STEP 1

Per implementare la validazione di Boostrap bisogna per prima cosa inserire nel tag `<form>`, il `novalidate` alla fine del form.

Esempio:

`<form class="needs-validation" action="{{route('beers.store')}}" method="post" novalidate>`

#### STEP 2
Dopo aver inserito il `novalidate` bisogna andare all'interno di ogni tag `<input>` che si desidera sia obbligatorio per l'utente ed aggiungere il `required`.

Esempio:

`<input  class="form-control" type="text" name="name" placeholder="Nome" required>`

#### STEP 3
Dopodichè inserire dopo il tag `<input>` un `div` con `class="invalid-feedback"` se si desidera segnalare l'errore, altrimenti se si vuole mostrare un messaggio di inserimento input corretto usare `class="valid-feedback"`.
All'interno del `div` in questione inserire il messaggio che si vuole mostrare all'utente.
se si vuole utilizzare tutti e due i controlli, inserire un `div` con `class="valid-feedback"` e subito sotto un'altro `div` con `class="invalid-feedback"`.

Esempio:

		<div class="form-group my-form">
            <label for="image">URL Immagine</label>
            <input class="form-control" type="text" name="image" placeholder="URL" required>
            <div class="invalid-feedback">
                Perfavore inserisci l' URL
            </div>
            <div class="valid-feddbak">
                Looks Great!
            </div>
        </div>


#### STEP 4 
Copiare ed incollora lo script js dalla documentazione di bootstrap, direttamente sotto il form nell'HTML.

Script:

	<script>
		// Example starter JavaScript for disabling form submissions if there are invalid fields
		(function() {
		'use strict';
		window.addEventListener('load', function() {
			// Fetch all the forms we want to apply custom Bootstrap validation styles to
			var forms = document.getElementsByClassName('needs-validation');
			// Loop over them and prevent submission
			var validation = Array.prototype.filter.call(forms, function(form) {
			form.addEventListener('submit', function(event) {
				if (form.checkValidity() === false) {
				event.preventDefault();
				event.stopPropagation();
				}
				form.classList.add('was-validated');
			}, false);
			});
		}, false);
		})();
	</script>

---

## INSERIRE UNA MODALE (POP-UP) BOOTSTRAP IN UN PROGETTO LARAVEL
Documentazione Modale : https://getbootstrap.com/docs/4.0/components/modal/


La modale di bootstrap funziona grazie a **due** componenti principali, il button con le classi di riferimento , e la modale pre-composta di bootstrap

*Consiglio*: La modale può essere messa in un file modal.blade.php a parte e poi essere richiamata nel codice principale con @include quando serve per tenere lo stesso più pulito.

**ATTENZIONE**
##### bisogna rendere univoche le classi della modale passando l'id dell'item sia nella modale che nel button!!!!!
  Questo è il codice del bottone con riferimento alla modale -->


    <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModalCenter{{$item->id}}">
      Cliccando qui si apre la modale
    </button>



 Questo è il codice della modale che può essere salvato nel file .php e richiamato con @include -->


          <div class="modal fade" id="exampleModalCenter{{$item->id}}" tabindex="-1" role="dialog" aria-labelledby="exampleModalCenterTitle" aria-hidden="true">
            <div class="modal-dialog modal-dialog-centered" role="document">
              <div class="modal-content">
                <div class="modal-header">
                  <h5 class="modal-title" id="exampleModalLongTitle">Titolo della modale</h5>
                  <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                    <span aria-hidden="true">&times;</span>
                  </button>
                </div>
                <div class="modal-body">
                 "testo della modale"
                </div>
                <div class="modal-footer">
                  <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                  <button type="button" class="btn btn-primary">Save changes</button>
                </div>
              </div>
            </div>
          </div>

Per far si che il codice funzioni bootstrap utilizza js, quindi bisogna ricordarsi di importare lo stesso nell'head della pagina principale utilizzando

    <script src="{{ asset('js/app.js') }}" defer></script>

se uniamo questa modale, assegnando a uno dei bottoni della stessa il type **'submit'**, e inserendo il tutto all'interno di un **form** possiamo utilizzarlo come step di conferma per l'utente su una determinata azione che vogliamo effettuare su db_. 

---

## CREARE UNA SEARCH BASE NELL'CRUD (LARAVEL) 

## STEP 1

Creare una search nel layout con metodo GET, e con un "name" che useremo come request

<form action="{{ route('root.index') }}" method="POST" role="search">
     @csrf
     @method("GET")
     <div class="input-group">
         <div class="form-outline">
             <input type="search" id="form1" class="form-control" name="item"
                 placeholder="Cerca item" />
         </div>
        <button type="submit" class="btn btn-primary">
            <i class="fas fa-search"></i>
        </button>
    </div>
</form>

## step 2

Far passare la ricchiesta all'index, verificarne l'esistenza, e filtrare con il metodo WHERE

public function index(Request $request)
    {

        $data = $request->all();

        if(empty($data["item"])){
            $beers = Beer::all();
        }
        if(!empty($data["item"])){
            $beers = Beer::where("name", "=", $data["item"])->get();
        }



        return view("beers.index", compact("beers"));
    }

---
## INIZIALIZZARE UN PROGETTO A GIT TRAMITE CMD

      cd laravel-boolean
      git init
      git remote add origin https://github.com/tuo-nome/nome-progetto.git
      git add .
      git commit -am "initial commit"
      git push --set-upstream origin main
      git push 

---


## Come inizializzare una tabella nel model senza sfruttare il plurale automatico di Laravel

In model inserire la proprietà

      protected $table= 'nome_tabella';

così laravel si abbina alla tabella chiamata come abbiamo deciso noi senza fare il pluarale

---
## DBAL E MODIFICA NELLE MIGRATION

#### In caso si verifichi l'errore 'Doctrine\DBAL\Driver\PDOMySql\Driver' not found”,
Nel file composer.json sostituire il doctrine/dbal da

    "doctrine/dbal": "^3.0",

a

    "doctrine/dbal": "^2.0",


Lanciare il comando

    composer require doctrine/dbal

nel **CMD**



quindi lanciare comando

    composer update 
---
---
## MIGRATION DI MODIFICA COLONNA ALLA TABELLA

#### AGGIUNGE UNA NUOVA COLONNA ALLA TABELLA
    "php artisan make":"migration add_votes_to_users_table --table=users"
    


#### AGGIORNA LA COLONNA DI UNA TABELLA
    php artisan make:migration update_description_in_products_table

    la migration è da compilare come nell'esempio

    
    <?php

      use Illuminate\Database\Migrations\Migration;
      use Illuminate\Database\Schema\Blueprint;
      use Illuminate\Support\Facades\Schema;

      class UpdateYearInVideogamesTable extends Migration
      {
          /**
          * Run the migrations.
          *
          * @return void
          */
          public function up()
          {
              Schema::table('videogames', function (Blueprint $table) {
                  $table->integer('year')->change();
              });
          }

          /**
          * Reverse the migrations.
          *
          * @return void
          */
          public function down()
          {
              Schema::table('videogames', function (Blueprint $table) {
                  $table->smallInteger('year')->change();
              });
          }
      }

#### AGGIORNA IL NOME DI UNA COLONNA DI UNA TABELLA

	"php artisan make":"migration rename_columnName_in_tableName_table --table=tableName"

la migration è da compilare come nell'esempio

       <?php

      use Illuminate\Database\Migrations\Migration;
      use Illuminate\Database\Schema\Blueprint;
      use Illuminate\Support\Facades\Schema;

      class UpdateYearInVideogamesTable extends Migration
      {
          /**
          * Run the migrations.
          *
          * @return void
          */
          public function up()
          {
                Schema::table('posts', function (Blueprint $table) {
                $table->renameColumn('vecchioNome', 'nuovoNome');
    });

          }

          /**
          * Reverse the migrations.
          *
          * @return void
          */
          public function down()
          {
              Schema::table('videogames', function (Blueprint $table) {
                  $table->renameColumn('nuovoNome', 'vecchioNome');
              });
          }
      }


#### ANNULLA L'ULTIMA MIGRATION ESEGUITA

    php artisan migrate:rollback

## IMPORTANTE!!!
Ricordarsi sempre che nel metodo "down" dobbiamo sempre mettere il contrario del metodo up, nell'esempio sopra per esempio stiamo trasformando una colonna che era smallInteger in una Integer, grazie al metodo down possiamo riportarla, in caso di necessità, ad essere di nuovo "smallInteger".
Oppure se creaimo una nuova colonna nel metodo "up", nel metodo "down" dovremo inserire il comando per eliminarla, come nell'esempio sotto.

        <?php

    use Illuminate\Database\Migrations\Migration;
    use Illuminate\Database\Schema\Blueprint;
    use Illuminate\Support\Facades\Schema;

    class AddYearToVideogamesTable extends Migration
    {
        /**
        * Run the migrations.
        *
        * @return void
        */
        public function up()
        {
            Schema::table('videogames', function (Blueprint $table) {
                $table->smallInteger('year');
            });
        }

        /**
        * Reverse the migrations.
        *
        * @return void
        */
        public function down()
        {
            Schema::table('videogames', function (Blueprint $table) {
                $table->dropColumn('year');
            });
        }
    }



---

## LARAVEL AUTHENTICATION

1. Nella cartella del progetto Laravel, a terminale: 

    ```
    composer require laravel/ui:2.4 // se non già fatto prima

    php artisan ui bootstrap --auth // attenzione: ricrea il file app.scss (quindi cancella gli import aggiuntivi come font awesome e partials) -> fare all'inizio, dopo Bootstrap
    
    npm install
    ```

    > Se, dopo aver eseguito il comando npm install, ci viene restituito l'errore `npm ERR! Unexpected end of JSON input while parsing near '...3.9.0","less-loader":'`, provare a risolvere con `npm cache clean --force`.

2. Lanciare la migration (creata automaticamente): `php artisan migrate`.

---

## SEEDERS AND FAKER
### Creare un seed che generi un numero a piacere di righe con valori generati automaticamente

1. creare il seeder:
`php artisan make:seeder NomeTabellaTableSeeder`

2. installare il faker:
`composer require fakerphp/faker`

3. se non ancora presente, creare il modello:
    - creare Model `php artisan make:model NomeModello`
    - in App / NomeModello.php (il Model), facciamo il match manuale della tabella (solo nel caso in cui nome tabella e nome modello nn siano stesso nome al plurale e al singolare) e creiamo le colonne della tabella
```
// nella classe NomeModello:
protected $table = 'nomeTabella'; // solo nel caso in cui nn sia mappata automaticamente
protected $fillable = ['nome_colonna1', 'nome_colonna2'];
```

4. nel seeder: 
```
// all'inizio del file
use App\NomeModello
use Faker\Generator as Faker

// in run
(Faker $faker)

for($i=0; $i < 100; $i++) {+
    $nomeOggetto = new NomeModello();
    $nomeOggetto->nome_colonna1 = $faker->name();
    $nomeOggetto->nome_colonna2 = rand(1200, 2000); // possiamo creare un simil faker
    // ...tutte le colonne che servono
    $nomeOggetto->save();
}
```

5. lancia il seeder: 
`php artisan db:seed --class=NomeTabellaTableSeeder`

---

## CREARE TRE TABELLE, COLLEGARLE TRA LORO CON RELAZIONI 1->1 E 1->*, E POPOLARLE CON UN SEEDER
> Nell'esempio, le tabelle fanno riferimento ad un ipotetico blog e sono le seguenti: authors, author_details, posts. 
La primary key di authors è la foreign key di author_details (relazione 1->1) e quella di posts (relazione 1->*).

1. creare il database.

2. creare i model e le migration (uno per tabella).
- posso creare model e migration allo stesso tempo (nome model: "Author") : `php artisan make:model Author --migration`; 
    - nella migration di Author:
        ```
        // nella migration creata aggiungiamo (fra id e timestamps):
        $table->string('name', 64);
        $table->string('surname', 64);
        $table->string('email', 64);

        // terminal, lanciare migration: 
        php artisan migrate
        ```
    - nella migration di AuthorDetail aggiungiamo la foreign key corrispondente alla primary key di author (id)
        ```
        $table->unsignedBigInteger('author_id') // author xé singolare della tabella authors
        // la foreign key si mette subito dopo l'id della tabella ospite

        // poi:
        $table->text('bio');
        $table->string('website', 2048);
        $table->string('pic', 2048);

        // alla fine, dopo timestamps, definiamo la foreign key, ovvero la colonna author_id che fa riferimento alla colonna id della tabella authors
        $table->foreign('author_id') 
        ->references('id')
        ->on('authors');
        
        // lancio la migration da terminale: 
        php artisan migrate
        ```
    - nella migration di Post ripeto quanto fatto prima, impostando le colonne della tabella e la foreign key (anche in questo caso riferita alla pk id di authors)
        ```
        $table->unsignedBigInteger('author_id') // author xé singolare della tabella authors
        // la foreign key si mette subito dopo l'id della tabella ospite

        // poi:
        $table->string('title', 255);
        $table->text('body');

        // alla fine, dopo timestamps, definiamo la foreign key, ovvero la colonna author_id che fa riferimento alla colonna id della tabella authors
        $table->foreign('author_id') 
        ->references('id')
        ->on('authors');
        
        // lancio la migration da terminale: 
        php artisan migrate

        ```
        > per correggere un errore in locale, prima di aver committato(video 10:19)


3. stabilisco le relazioni tra le tabelle
    - A) all'interno del model Author, indico il tipo di relazione fra questa tabella e le altre. Ciò mi permetterà di prendere i dati delle altre tabelle direttamente da Author (grazie al tipo di relazione e alla foreign key)
        ```
        // funzione che collega il model Author ad AuthorDetail
        public function detail() { // nome descrittivo a piacere
            return $this->hasOne('App\AuthorDetail); // indica relazione 1->1 (author ha un solo dettaglio) e namespace
            // si può anche usare il metodo magico di php `AuthorDetail::class` senza apici (in questo caso, lo "use" all'inizio del file non serve)
        }

        // funzione che collega il model Author a Post
        public function posts() {
            return $this->hasMany('App\Post'); // indica relazione 1->*
        }
        ```

    - B) nel model AuthorDetail metto un metodo che indica la sua appartenenza a Author
        ```
        public function author() {
            return $this->belongsTo('App\Author');
        }
        ```

    - C) nel model Post metto un metodo che indica la sua appartenenza a Author
        ```
        public function author() {
            return $this->belongsTo('App\Author');
        }
        ```

4. creare il seeder e installare il fake
    - seeder: `php artisan make:seeder PostSeeder` // lo userò per inserire i dati di entrambe le tabelle
    > creerò + seeder e in seeds/DatabaseSeeder si fa un riferimento a tutti i seeder, poi per lanciarli tutti insieme chiameremo il DatabaseSeeder (avendo creati i singoli, posso anche lanciare solo quello che mi interessa.

    - faker: `composer require fakerphp/faker`
    - popolo il seeder:
        ```
        // all'inizio
        use Faker\Generator as Faker;
        use App\Author;
        use App\AuthorDetail;
        use App\Post;

        // parametri funzione
        run(Faker $faker)

        // corpo della funzione:
        {

            // usare un for per creare più utenti
            for($i = 0; $i < 20: $i++) {

                // creare un oggetto dove c'è la primary key
                $author = new Author();
                $author->name = $faker->firstNmame();
                $author->surname = $faker->lastName();
                $author->email = $faker->email();
                $author->save();

                // creare l'oggetto collegato dalla foreign key
                $authorDetail = new AuthorDetail();
                $authorDetail->bio = $faker->text();
                $authorDetail->website = $faker->url();
                $authorDetail->pic = 'https://picsum.photos/seed/' . rand(0, 1000) . '/200/300'; // widht e length
                
                // creo più post per autore
                for($l = 0; $l < rand(2, 5); $l++) {
                    $post = new Post();
                    $post->title= $faker->text(20);
                    $post->body= $faker->text(1000);
                    $author->posts()->save($post);
                }

                // va nell'autore, prende il suo dettaglio (il metodo creato in Author) e salva i dati appena creati
                $author->detail()->save($authorDetail); // corrisponde a $authorDetail->author_id = $author->id + save
            }
            
        }

        // lancio il seeder
        php artisan db:seed --class=PostSeeder
        ```

---

## CREARE UNA TABELLA (TAGS) E COLLEGARLA AD UN'ALTRA ESISTENTE TRAMITE RELAZIONE MANY TO MANY
> Stiamo simulando un blog (es. iniziato con scheda 89): creeremo la tabella tags che si collegherà all'esistente tabella posts con relazione many to many
> La relazione *->* richiede una tabella che faccia da intermediario e che conservi le fk di posts e di tags collegate tra loro (possono essere tabelle molto lunghe). Il nome della tabella è al singolare: post_tag (video: 11:10).
> Le tabelle sono create dalle migration, ma sono i model a stabilire le relazioni fra esse.

1. Creare la tabella tags 
    - a) creare la migration e il modello della tabella tags: `php artisan make:model Tag --migration`
        > Esiste anche una versione compatta: `php artisan make:model Tag -m`
        > Se volessimo toglier il timestamps (nn crea mai problemi, ma nella tabella intermedia si pò togliere xé nn ha reale motivo di esistere), cancellarlo dalla migration e nel model (se c'è), nella classe scrivo public $timestamps = false
    
    - b) definire le colonne della tabella tags:
        ```
        //Nella migration di tags, tra id e timestamps:  
        $table->string('name', 64);

        // lanciare la migration da terminale per creare la tabella
        php artisan migrate
        ```

2. Creare la tabella intermedia (post_tag) e definirne le colonne tramite migration
    > Il nome segue questo schema: nome model 1a entità_nome model 2a entità, entrambe al singolare e minuscole
    - a) creo la tabella da terminale: `php artisan make:migration create_post_tag_table`
    - b) all'interno della migration di post_tag:
        ```
        // tra id e timestamps
        $table->unsignedBigInteger('post_id'); // foreign key che collega posts
        $table->unsignedBigInteger('tag_id'); // foreign key che collega tags
        
        // dopo tutte le proprietà/colonne, definire le foreign keys
        $table->foreign('post_id')
        ->references('id')
        ->on('posts');

        $table->foreign('tag_id')
        ->references('id')
        ->on('tags');

        ```
    - c) lanciare la migration per creare la tabella post_tag: `php artisan migrate`

3. Stabilire le relazioni (many to many) fra le tabelle posts e tags tramite i rispettivi modelli
    - a) in Post.php, dopo la funzione esistente ("author"):
        ```
        public function tags() {
            return $this->belongsToMany('App\Tag'); // stabilisce relazione con il model Tag
        }
        ``` 
    - b) in Tag.php, lo stesso:
        ```
        public function posts() {
            return $this->belongsToMany('App\Post'); // stabilisce relazione con il model Post
        }
        ```
    > ripasso sulle relazioni: https://laravel.com/docs/7.x/eloquent-relationships (nn guardare i polymorphic)

4. Popolare di dati la tabella tags tramite seeder
    > uso un seeder dedicato, ma potevo usare quello già presente per le altre tabelle
    a) creare il seeder TagSeeder: `php artisan make:seeder TagSeeder`
    b) all'interno del seeder:
        ```
        // all'inizio definisco il namespace
        use App\Tag;

        // all'interno di run():
        $tags = ['sport', calcio, gossip, tecnologia, spazio, salute, economia, cronaca];

        foreach($tags as $tag) {
            $tagDB = new Tag();
            $tagDB->name = $tag;
            $tagDB->save();
        }

        // lanciare il seeder da terminale: 
        php artisan db:seed --class=TagSeeder
        ```

## VISUALIZZARE I DATI DELLA TABELLA TAGS PRECEDENTEMENTE CREATA
### Scopo: passare i tags e l'autore nel form che permette la creazione dei post, così da aggiungerli (tramite due select) ad ogni post creato. L'autore e i tag selezionati verranno poi visualizzati insieme al relativo post.

> !! Cambiare tutte le route "post" create precedentemente in posts !!

1. Completare le funzioni create e store della crud di Post
    > il form di create avrà le seguenti caratteristiche: 
        - un input per il titolo del post, 
        - una textarea per il suo contenuto, 
        - un select per l'autore del post, 
        - un select multiplo per i tag relativi

    - a) in PostController 
        - in create, prendere i dati delle tabelle authors e tags e renderli disponibili alla view con il form:
            ```
            // all'inizio
            use App\Author;
            use App\Tag;

            // nel corpo della fn:
            $authors = Author::all(); // prendo i dati dalla tabella author
            $tags = Tag::all(); // prendo tutti i tags tramite il modello Tag
            return view('post.create', compact('authors', 'tags')); // passo i dati al form
            ```
        - in store, passo i dati al db
            ```
            // passo il post
            $data = $request->all();

                /*  // opzionale: qui eventuale validazione per evitare manipolazioni lato browser del value "author_id" inviato con select del form
                    $author_id = data['author_id'];
                    if((!Author::find($author_id)) {
                        dd('check stupidello');
                        // ...redirect verso pagina di cortesia
                    }; 
                    // video: 10:39 
                */

            $post = new Post();
            $post->fill($data);
            $post->save();

            // insieme al post passo anche i tags
            $post->tags()->attach($data['tags']); // attach: metodo di laravel, accetta sia valori singoli sia array (anche array di oggetti), stabilisce relazioni multiple e salva in automatico

            // reindirizzo alla pagina con tutti i post
            return redirect()->route('posts.index'); 
            ```
    - b) in Post imposto la variabile per usare fill()
        ```
        // all'interno della classe, prima delle altre funzioni:
        protected $fillable = ['title', 'body', 'author_id']; // tutti i campi della tabella posts, compresa la fk (author_id)
        ```

2. Creare il form per l'aggiunta dei post
    - a) in views/post creare il file create.blade.php, prepararlo con extend e section, comporre un form bootstrap con le caratteristiche elencate all'inizio
        - il form ha action = "{{route('posts.store)}}", method="post", @csrf, @method('POST')
        - l'input title ha name="title"
        - la textarea ha name="body"
        - la select per gli autori:
            ```
            select: name="author_id" // è il campo dell fk che collega le tabelle authors e posts
                @foreach($authors as $author)
                    // passiamo l'id (che finirà nella colonna "author_id") ma visualizziamo nome e cognome dell'autore
                    option: value="{{$author->id}}" >{{$author-> name}} {{author->surname}}<
            ```
            > recap video: 10:35
        - la select multipla per i tags (attributo "multiple" di bootstrap):
            ```
            select: name="tags[]" // [] segnala che sto passando un array
                @foreach($tags as $tag)
                    option: value={{tag->id}} >{{tag->name}} // come per la select precedente
            ```
    - b) in views/post/index, mostrare i tags relativi ad ogni commento
        ```
        // aggiungere un th "tags" all'interno di thead
        // aggiungere un td:
        $foreach ($post->tags as $tag) // raggiungo i tags tramite la relazione *->* impostata precedentemente con la tabella posts
        {{$tag->name}}, 
        ```

