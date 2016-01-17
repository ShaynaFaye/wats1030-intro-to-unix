# Stretch Goals for the *nix Scavenger Hunt

The following goals are meant to provide a way for more experienced users to
extend their knowledge of the *nix command line.

* Use `curl` to look up the URL `http://www.imdb.com/title/tt0070948/`. The title of this film will lead you to the answer. *What is the answer?*

Command:  'curl -X POST http://www.imdb.com/title/tt0070948/ | more'.  I originally ran this command without the '| more' and it displayed a lot of information.  It was the entire html document for that web address.  I couldn't even scroll all the way up to the top.  So I tried the command again with the added '| more' command so that it would display the information paginated and I could more easily page down to view the content.  This allowed me to view and start at the top of the html document and not too far down I saw "<title>Zardoz (1974) - IMDb</title>".  So the title of the film is Zardoz. 