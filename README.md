# ACME Shop
![acme_shop](https://user-images.githubusercontent.com/79991821/149802185-f5924eb6-ec12-468d-b113-d3ce3fb31c62.JPG)
## Overview del progetto

Questo progetto simula una pagina di visualizzazione prodotto in un sito e-commerce, dove l'utente può visionare diversi modelli del prodotto in vendita.


![mug_modello1](https://user-images.githubusercontent.com/79991821/149802560-d6d0397d-d566-4037-98d8-0596fb545a1b.JPG) ![mug_modello2](https://user-images.githubusercontent.com/79991821/149802606-6d2ab1a3-dc8e-4766-b963-d4201635efdd.jpg)![mug_modello3](https://user-images.githubusercontent.com/79991821/149802627-9c386458-e33d-4a4b-b7ca-dfe7a7a8ef1b.JPG)

## Elementi del progetto

- ASPETTO: il progetto è costruito per sembrare verosimile a una pagina di visualizzazione di un prodotto che potremmo trovare in un sito commerciale. A tale scopo sono stati aggiunti: il titolo della finestra di navigazione ed elementi grafici per formare un titolo che contestualizzi il prodotto. 

- MODELLO: il modello scelto è quello di una tazza, non è molto complesso (1200 vertici) ed è accompagnato dalla normal map. Ho deciso di utilizzare due materiali diversi: il primo è uno ShaderMaterial per il quale ho adattato lo shader di un esercizio visto a lezione (17-glossy-reflectionMapping.html) e il secondo è un MeshPhongMaterial. Questa scelta nasce per sperimentare entrambi gli approcci alla personalizzazione del materiale: scrivendo uno shader personalizzato e senza farlo. 
SHADERMATERIAL: il risultato finale che si voleva ottenere è quello di una tazza realistica con finitura lucida, ma non sono riuscita ad ottenere l'effetto sperato. Ciò che vediamo a schermo è comunque un risultato esteticamente gradevole, ma che risulta più artificioso (una plastica molto opaca e ruvida). Ho deciso di personalizzare questo shader non utilizzando una texture, ma applicando un colore calcolato all'interno dello shader stesso. Per fare questo ho creato una variabile colore che utilizza la funzione mix(). Questa funzione mescola i due colori dati in input secondo un certo valore percentuale. L'elemento che determina la sfumatura è proprio quest'ultimo, perchè essendo legato ad una delle coordinate del vertice varia in base alla posizione di esso. In questo caso ho legato questo valore alla coordinata -y in modo che la sfumatura si sviluppasse nell'altezza dell'oggetto. Inoltre ho smorzato questo parametro moltiplicandolo per 0.5 in modo che la sfumatura di colore non risultasse troppo poco morbida. Infine ho combinato il colore ottenuto con la outRadiance che avremmo ottenuto normalmente da questo shader.
MESHPHONGMATERIAL: questo tipo di materiale, più intuitivo da utilizzare, permette di agire direttamente su attributi prestabiliti che caratterizzano il materiale. Per creare l'effetto di lucentezza tipico di un oggetto di ceramica smaltata ho agito su due attributi in particolare: specular e shininess. Il primo determina il colore del riflesso dell'oggetto, mentre il secondo determina la lucentezza del materiale (più il suo valore è alto maggiore sarà la riflessione). Inoltre ho associato a questo materiale una normal map diversa da quella di default per avere una netta differenza e non un semplice cambio di colore tra un modello e l'altro.  

- CUBEMAP: la cube map determina l'aspetto dello sfondo ma agisce anche sull'illuminazione della scena.

-INTERFACCIA: per rendere la scena interattiva ho sfruttato l'evento 'onclick' associato a dei bottoni visualizzati a schermo. La variabile 'choice' è adibita a conservare la scelta fatta dall'utente(viene aggiornata ad ogni click) per poi essere inserita in un costrutto switch per determinare quale cambiamento apportare. I bottoni sono stati poi personalizzati usando il CSS. Il modello è ispezionabile con il mouse a 360° 


## Prestazioni

Il frame rate rimane sempre molto alto, attorno ai 60fps, anche in situazioni di stress come il movimento esagerato della camera o la scelta di diversi modelli.

## Credits

 Skybox:    [humble_bk] https://opengameart.org/node/28758
            [humble_dn] https://opengameart.org/node/28759
            [humble_ft] https://opengameart.org/node/28760
            [humble_lf] https://opengameart.org/node/28761
            [humble_rt] https://opengameart.org/node/28762
            [humble_up] https://opengameart.org/node/28763

modello tazza: https://sketchfab.com/3d-models/mug-4-dde2b6ecff054aa8ad19f3aeb0cf9651

fonte fragmentShader: https://thebookofshaders.com/glossary/?search=mix +  esercizio 17-glossy-reflectionMapping.html
                       
modello tazza e Mug4_normal.png: https://sketchfab.com/3d-models/mug-4-dde2b6ecff054aa8ad19f3aeb0cf9651
    

NormalMap.png: photo by Mitchell Luo from Pexels: https://www.pexels.com/photo/white-and-brown-striped-textile-3694711/
trasformata con normal map online con https://cpetry.github.io/NormalMap-Online/

grafiche create con pixlr: https://pixlr.com/it/ 
