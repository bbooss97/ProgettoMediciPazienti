# README

6.3 Distribuzione ed installazione dell’applicazione
L’applicazione è realizzata a partire da Ruby on Rails ed è quindi necessario installare questo framework oltre che all’interprete Ruby.

Per il corretto funzionamento dell’applicazione è necessario installare Ruby 3.0.0 ( è fondamentale questa versione per risolvere problemi di compatibilità del gemfile ruby) reperibile comodamente da internet.

Installare in seguito il framework Rails attraverso il comando gem install rails eseguibile da riga di comando.

Installare sqlite3 v 1.4.2 .

Installare node.js e yarn per il corretto funzionamento del webpacker.

6.4 Dimostrazione a partire da git
Per eseguire l’applicazione una volta scaricate ed installate tutte le componenti sopra citate è necessario fare la clone della repository github …  ed estrarre lo zip contenente il progetto.
Dirigersi con la console all’interno della cartella unzippata ed eseguire il comando bundle install.
Se si verificano problemi con sqlite3 è necessario scaricare questa componente e scompattare e dll e gli eseguibili reperibili nella cartella windows 32.
Una volta fatto ciò è necessario risolvere problemi legati al webpacker andandolo a reinstallare attraverso i seguenti comandi:

rm -rf bin/webpack*
rails webpacker:install
RAILS_ENV=production rails webpacker:compile
 
Una volta fatto ciò per far funzionare l’Oauth di Facebook è necessario generare una migration con il comando:
 
rails g migration AddOmniauthToPazientes provider:string uid:string

Lanciare infine i comandi :
 
bundle install 
rails db:migrate
 
Adesso l’applicazione è pronta per essere utilizzata ed il server è lanciabile col comando rails s.
