...Le richieste e risposte sono del protocollo HTTP..

### Classi lato server
ListaDiPrelievo(
    list of RigaLista,
    impegnata,
    id_operatore

)
RigaLista(
    indice,
    materiale,
    quantità,
    completata,
)


### API lato server

CreaUDC:
-> Richiesta(id_operatore)
<- Risposta(numero_udc)

AggiungiMaterialeAUDC:
-> Richiesta(numero_udc, id_materiale, quantità, id_operatore)
<- Risposta()

AggiungiNuovoMateriale:
-> Richiesta(id_materiale, peso, altezza, lunghezza, profondità, note)
<- Risposta()

EliminaUDC:
-> Richiesta(numero_udc, id_operatore)
<- Risposta()

SpostaUDC:
-> Richiesta(numero_udc, pos_finale, id_operatore)
<- Risposta()

OttieniListeDiPrelievo
-> Richiesta(id_operatore)
<- Risposta(ListeDiPrelievo)

IniziaListaDiPrelievo
-> Richiesta(id_operatore, id_lista)
<- Risposta(lista_operazioni)

Picking
-> Richiesta(id_operatore, numero_udc, id_materiale, quantità)
<- Risposta()

CompletataRigaLista
-> Richiesta(id_operatore, id_lista, indice_riga)
<- Risposta()

CompletaLista
-> Richiesta(id_operatore, id_lista)
<- Risposta()

Da aggiungere{
    interrogazionePosizione
    interrogazioneUDC
    interrogazioneMateriale
    Funzioni per creare utenti
}
