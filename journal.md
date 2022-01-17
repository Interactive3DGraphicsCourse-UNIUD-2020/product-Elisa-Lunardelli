# journal

## Scelte di design

Come primo passo ho deciso un tema per questo progetto. Vedendo la grande disponibilità di modelli 3D sul web relativi all'arredamento ho deciso di trattare un prodotto casalingo facendo ricadere la mia scelta su una tazza (un modello facile da gestire per me). 

Il passo successivo è stato creare un'immagine per il titolo, mantenendo uno stile semplice e pulito dando un nome al sito su cui si visualizza il prodotto.

Ho deciso di tenere il canvas della stessa grandezza della finestra, perchè rinchiudere il prodotto all'interno di un frame circoscritto, immerso in uno sfondo stastico, mi sembrava un design un po' datato, inoltre il progetto visualizzato a schermo intero sarebbe risultato un po' vuoto e spoglio. Inizialmente avevo pensato di rendere il canvas trasparente e sovrapporre solo il modello renderizzato ad una pagina web statica come si vede in molti siti, dovendo però utilizzare una environment map ho deciso di sfruttarla per lo sfondo. Visto il tema del mio progetto, volevo utilizzare una cube map dell'interno di una casa, ma non riuscendo a trovare quello che cercavo ho ripiegato su uno sfondo neutro, ma gradevole.

Per poter sovrapporre elementi html al canvas e per poter personalizzare lo stile di questi elementi ho utilizzato css. 


## Problematiche di realizzazione

- SCRITTURA DEGLI SHADER: non sono riuscita a scrivere uno shader che restituisse un effetto smaltato. Dopo alcune considerazioni credo che questo problema sia dato dalla cube map, perchè non sembrerebbe contribuire all'illuminazione. Altro indizio a questa ipotesi è che al variare del parametro di roughness l'effetto visivo di ruvidezza non migliora anzi va solo a scurire il colore del modello. Una volta creato il secondo materiale di tipo Phong ho dovuto aggiungere delle luci aggiuntive perchè potesse restituire l'aspetto desiderato. 




