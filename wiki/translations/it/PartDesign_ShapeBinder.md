---
- GuiCommand:/it
   Name:PartDesign_ShapeBinder
   Name/it:Forme legate
   Workbenches:[PartDesign](PartDesign_Workbench/it.md)
   MenuLocation:Part Design → forme legate
   Version:0.17
   SeeAlso:[PartDesign Forme legate secondarie](PartDesign_SubShapeBinder/it.md),
 [Clone](PartDesign_Clone/it.md)
---

# PartDesign ShapeBinder/it

## Descrizione

Crea un riferimento **shape binder** (forma legata) all\'interno del corpo attivo. Una forma legata è un oggetto di riferimento che si collega a bordi o alle facce di un altro corpo. Può anche essere usato per collegare uno schizzo da un corpo a un altro corpo. L\'oggetto forma legata viene visualizzato in giallo traslucido nella [Vista 3D](3D_view/it.md).

Un esempio di utilizzo potrebbe essere la costruzione di una scatola con copertura adatta a due corpi diversi o la realizzazione di fori allineati tra corpi diversi.

<img alt="" src=images/Shapebinder_tree.png ) ![](images/Shapebinder_flow.png  style="width:600px;"> 
*Sono selezionate due forme da Body.Pad004 e i relativi oggetti di riferimento sono ora disponibili in Body001.Sketch005 come geometria esterna tramite Body001.ShapeBinder.*

## Utilizzo


<div class="mw-translate-fuzzy">

Uso generale:

1.  Attivare il corpo destinatario (corpo che deve ricevere l\'oggetto forma legata).
2.  Premere il pulsante **<img src="images/PartDesign_ShapeBinder.svg" width=24px> '''Forma legata'''**.
3.  Premere il pulsante **Oggetto** o il pulsante **Aggiungi geometria**.
4.  Nella vista 3D, selezionare l\'oggetto o la geometria da copiare. *Oggetto* seleziona l\'intero corpo; *Aggiungi geometria* seleziona qualsiasi elemento (vertice, bordo, faccia).
5.  Per rimuovere la geometria selezionata, premere il pulsante **Rimuovi geometria** e selezionare la geometria nella vista 3D. Per annullare, premere nuovamente il pulsante.
6.  In alternativa, è possibile selezionare il corpo da copiare prima di avviare il comando Forma legata.
7.  Premere **OK**.


</div>

**Esempio**

:   L\'esempio utilizza la funzione ShapeBinder per praticare un foro (con o senza filettatura) attraverso più di un corpo. Normalmente la funzione Foro di Part Design è limitata a un singolo corpo. L\'esempio usa due cubi uno di fronte all\'altro ma disallineati in modo arbitrario. I fori vengono creati con schizzi contenenti un cerchio per ogni foro (il diametro viene ignorato dalla funzione foro). Quando si copia lo schizzo sull\'altro cubo, sarà nella stessa posizione nel sistema di coordinate del cubo locale. Nell\'immagine questo è mostrato dal cerchio bianco sul cubo posteriore. Questo non è ciò che vogliamo, perché il foro in quella posizione non sarebbe allineato al foro nel cubo anteriore.





:   

    :   ![](images/ShapeBinderThroughHole.png )
    :   *Esempio di configurazione per mostrare come eseguire fori attraverso corpi diversi. Il cerchio bianco mostra che copiare gli schizzi non è sufficiente*


<div class="mw-translate-fuzzy">

Ecco come utilizzare la funzione ShapeBinder per ottenerlo:

1.  Preparare una scena come da immagine sopra. Se si utilizzano i cubi di [Part](Part_Workbench/it.md), ricordare che è necessario inserirli in un contenitore \"Corpo\". Ognuno in un contenitore a corpo singolo. Altrimenti le funzioni di [PartDesign](PartDesign_Workbench/it.md) non funzionano. Se si costruiscono da schizzi, il sistema dovrebbe creare i contenitori dei corpi di default.
2.  selezionare la scheda Proprietà Dati per spostare il secondo cubo in modo che tocchi il primo cubo con uno spostamento laterale.
3.  attivare l\'ambiente PartDesign
4.  creare uno schizzo sulla faccia frontale del primo cubo e posizionare un cerchio ovunque e poi chiudere lo schizzo
5.  selezionare lo schizzo nella struttura e premere il pulsante [Foro](PartDesign_Hole/it.md). Prima di assicurarsi che il primo corpo sia il corpo attivo (doppio clic).
6.  selezionare un foro di dimensioni adeguate. Nellimmagine sopra è stato selezionato anche l\'alesaggio. Chiudere la funzione [Foro](PartDesign_Hole/it.md).

    :   Ora l\'immagine dovrebbe apparire come sopra. Quando si nasconde il primo cubo (selezionarlo e premere spazio) si può vedere che il buco non raggiunge il secondo cubo. Non lo farà, anche quando si seleziona \"Attraverso tutto\" o quando si immette una distanza molto grande nella finestra di dialogo del [foro](PartDesign_Hole/it.md). La finestra di dialogo del foro è sempre limitata a un singolo corpo.
    :   Ecco dove entra in gioco ShapeBinder.
7.  Per prima cosa selezionare il cubo posteriore. Questo è l\'obiettivo a cui verrà aggiunto ShapeBinder. Deve essere attivato, quindi assicurarsi di aver fatto doppio clic.
8.  Nella struttura selezionare lo schizzo usato per il foro. È importante non attivare il primo corpo.
9.  Selezionare la funzione ShapeBinder.

    :   Si dovrebbe aprire una finestra di dialogo. Nella riga \"Oggetto\" dovrebbe essere visibile il nome dello schizzo. Se fosse stata selezionata la funzione senza selezionare lo schizzo, è possibile premere \"Oggetto\" e quindi selezionare lo schizzo dall\'elenco. Si consiglia di selezionarlo prima per ottenere quello giusto, soprattutto se si hanno molti schizzi con nomi generati automaticamente Sketch001, \... \"Aggiungi geometria\" non è utile in questo caso, perché si vuole selezionare l\'intero schizzo. \"Aggiungi geometria\" viene utilizzato se si devono selezionare solo delle parti.
10. Premere **OK** per chiudere la funzione di schizzo e verificare che un nuovo elemento sia stato aggiunto all\'albero del secondo cubo.

    :   Quando si attiva o disattiva la visibilità di ShapeBinder, questo viene visualizzato in giallo nella [vista 3D](3D_view/it.md). Tuttavia è nella posizione sbagliata, proprio come il cerchio bianco nell\'immagine sopra. Ciò è dovuto all\'impostazione di default del parametro Trace.
11. Nelle proprietà di ShapeBinder nella scheda Dati impostare il parametro **Trace Support** su true. L\'impostazione predefinita era false.

    :   Con **Trace Support** su true, ShapeBinder non viene influenzato dalle trasformazioni locali del corpo di destinazione, ad es. le traslazioni fatte prima. La forma rimane esattamente nella posizione della forma originale dell\'oggetto. Provare a spostare l\'oggetto per vedere che ShapeBinder segue sempre la nuova posizione.
    :   Purtroppo non si può selezionare ShapeBinder per un [foro](PartDesign_Hole/it.md). Pertanto bisogna creare uno schizzo locale e usarlo per il nostro bucoforo nel secondo cubo.
12. Selezionare la faccia anteriore del cubo posteriore e creare un nuovo schizzo (fare clic su **OK** per il suggerimento nella finestra di dialogo)
13. Rendere invisibile tutta la geometria e visibile ShapeBinder. Ora si può utilizzare la funzione geometria esterna e selezionare il cerchio nel raccoglitore forma. Serve il punto centrale di quel cerchio.
14. Creare un nuovo cerchio e posizionarlo nel punto centrale del cerchio di ShapeBinder. Il raggio non è importante. La funzione [Foro](PartDesign_Hole/it.md) utilizza solo i punti centrali dei cerchi (nota: i singoli punti vengono ignorati dalla funzione Hole, bisogna usare i cerchi)
15. Chiudere lo schizzo e fare clic su [Foro](PartDesign_Hole/it.md). Impostare la finestra di dialogo sugli stessi valori del foro iniziale e premere OK.


</div>


<div class="mw-translate-fuzzy">

Fatto.

:   Ora i due fori sono collegati in due corpi diversi. Se si modifica la geometria o le posizioni dei fori, entrambi i fori si adatteranno. Solo quando si aggiunge un nuovo foro, bisogna aggiornare lo schizzo nel secondo cubo per il secondo foro.


</div>


<div class="mw-translate-fuzzy">


:   Notare
:   che esiste un altro modo per creare uno ShapeBinder: con il cubo posteriore attivato, fare clic sulla faccia anteriore del cubo anteriore e creare un nuovo schizzo. Appare una finestra di dialogo in cui si seleziona \"Schizzo dipendente\". Ciò crea effettivamente un raccoglitore di forme. È possibile visualizzare il parametro **Supporto traccia** nella finestra delle proprietà. Sono pochi clic in meno rispetto alla nostra procedura.
:   Notare inoltre che usare ShapeBinder con gli schizzi è solo un sottoinsieme delle sue capacità. È anche possibile utilizzare parti della geometria 3D come mostrato nell\'esempio sopra.


</div>

## Opzioni

Fare doppio clic sull\'etichetta ShapeBinder nell\'albero del modello o fare clic con il tasto destro e selezionare **Modifica forma legata** nel menu contestuale per modificarne i parametri.

## Proprietà


<div class="mw-translate-fuzzy">

-    {{PropertyData/it|Label}}: nome dato all\'oggetto, questo nome può essere cambiato a piacere.

-    **Trace Support**: Impostando questa opzione su true, Shapebinder osserva i posizionamenti relativi delle parti e dei corpi. L\'impostazione predefinita è false. Vedere l\'esempio sopra per come funziona. {{Version/it|0.18}}


</div>

## Limitazioni


<div class="mw-translate-fuzzy">

-   La selezione multipla non è supportata. Per ogni singola selezione devono essere premuti i pulsanti Aggiungi geometria e Rimuovi geometria.

C\'è una soluzione alternativa per la selezione multipla: selezionando tutti gli elementi che si vogliono ottenere prima di creare lo ShapeBinder, questi vengono visualizzati nell\'elenco iniziale.

-   Una forma legata non può fungere da base per una funzione.
-   La geometria selezionata su un corpo deve essere contigua.
-   Se il corpo da copiare viene selezionato prima di avviare il comando, o se viene utilizzato il pulsante **Object**, non è più possibile selezionare solo specifici elementi di geometria.
-   La posizione relativa del corpo destinatario e del corpo copiato non viene presa in considerazione. forma legata adotta le stesse coordinate interne del corpo copiato. Dalla versione 0.18 ha una nuova proprietà \"Trace Support\", che permette di cambiare questo comportamento e prendere in considerazione i posizionamenti relativi.


</div>


<div class="mw-translate-fuzzy">





</div>


{{PartDesign Tools navi

}}



---
![](images/Right_arrow.png) [documentation index](../README.md) > [PartDesign](PartDesign_Workbench.md) > PartDesign ShapeBinder/it
