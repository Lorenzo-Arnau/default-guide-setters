<!-- ✨ Magic ✨ -->

### Puoi cercare CDN qui

- [JSDELIVER](https://www.jsdelivr.com/)  

---

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