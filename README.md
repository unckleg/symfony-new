- Prvo preko terminala dodjite do foldera projekta i preko composer-a instalirajte FosUserBundle
	```
	composer require friendsofsymfony/user-bundle "~2.0"
	```

- Nakon toga preko Netbeans-a nadjite fajl AppKernel.php (projekat/app/AppKernel.php) i u njega dodajte na kraj
   ```ruby
    new FOS\UserBundle\FOSUserBundle() 
    ```

- Kreirajte novi entitet nek se zove User (i pogledajte sta sam tamo ispisao u AppBundle/Entity/AppUser) 

- Udjite u projekat/app/security.yml i pogledajte kako sam ja odradio mozete slobodno sve da iskopirate i zamenite sa defaultnim podesavanjaima.
- Udjite u projekat/app/config.yml i pronadjite dole #FOSUser Configuration i podesite to kao sto sam ja odradio

- Udjite u projekat/src/AppBundle/Controller/admin i napravite jedan SecurityController (Pogledajte kako sam ja isti odradio i iskopirajte slobodno)
	Takodje napravite u routing-u 3 rute nove (login, logout, auth: pogledajte kako sam ja to odradio u AppBundle/Resources/config/routing/admin/routing.yml)

- Udjite u projekat/src/AppBundle/Resources/views/admin i napravite novi folder security u njemu napravite view/twig skriptu index.html.twig
 	Pogledajte kako sam ja svoju odradio i odradite isto. 

- Na kraju udjite preko konzole i unesite ovih par komandi:
```ruby
	- php bin/console cache:clear --env=dev
	- php bin/console cache:clear --env=prod
	- php bin/console fos:user:create (Ova komanda je za kreiranje user-a)
	- php bin/console fos:user:promote (Unesite vas username i stavite sebi rolu: ROLE_ADMIN)
```

# Voila!
