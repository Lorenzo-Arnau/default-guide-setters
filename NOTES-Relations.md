ogni utente ha uno o + post

<!-- $table->caratterisctiche(use_id) -->
relazione one to many: utente e post
relazione one to one: utente e dettagli utente

si mette la foreign key (che è la primary key di utente) nelle altre 2 entità
- versione estesa e contratta: da preferire quella estesa

la foreign key va definita anche nella tabella ospite con le stesse caratteristiche della primary key

1. creiamo db "boolpress"

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
    - A) all'interno del model di Author, indico il tipo di relazione fra questa tabella e le altre. Ciò mi permetterà di prendere i dati delle altre tabelle direttamente da Author (grazie al tipo di relazione e alla foreign key)
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
    <!-- // installare generatore random di immagini composer require woodsandwalker/faker-picture -->
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
            <!-- $faker->addProvider(new WW\Faker\Provider\Picture($faker)); // genera immagini randomiche per utente -->

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

    > recap (video 11:10)

4. installare bootstrap

5. creare il controller: `php artisan make:controller AuthorController`;
    > non usiamo la crud con resource perché nn utilizziamo tutti i metodi e rimarrebbero delle route vuote
    - nel controller:
        ```
        // sopra
        use App\Author

        // creo la funzione index e al suo interno:
        public function index() {
            $authors =  Author::all();
            Route::get('/author', 'AuthorController@index');
        }
        ```

// faremo la crud riferita alla tabella authors e, nel create, manualmente prenderemo le proprietà collegate (tabella author_details), quindi non useremo fill()

// in AuthorController.index:
return view('author.index', compact('authors));

// in views: author/incdex.blade.php
// copio una tabella bootstrap
con un foreach accedo ai dettagli
foreach($authors as $author)
    @dump($author->detail->pic)
@endforeach
// tabella, th
#, name, surnanme, emaill, bio, website, pic
// tabella, td
foreach($authors as $author)
    <tr>
     <td>{{author->id}}
     ...
     td {{author->detail->bio}}
@endforeach

// creo un base con tutti gli asset, mix, yield





// se devo svuotare le tabelle nel db con il truncate, partire da quelle con le foreign key, lasciare quella con la pk per ultima; togliere il flag enable fk da phpadmin

// se ci sono dei problemi dopo il rename, `composer install` x rimappare tutto


// imposto la crud
php artisan make:controller --resource PostController

// in web.php:
Route::resource('post', PostController::class);

// in PostController.index
use App\Post
$posts = Post::all();
return view('post.index', compact('posts));

// in views: 
creo post/index.blade.php;
all'interno: altra tabella bootstrap;
th: #, title, body, author(nome e cognome insieme)
td: 
```
@foreach($post as $posts)
tr
td {{$post->id}}
td {{$post->title}}
td {{$post->body}}
td {{$post->author->name}} {{$post->author->surname}}
```