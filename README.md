@startuml

title:Sync PostSectorClothing

participant "Totem Cliente" as Totem
participant "Api Elis 2" as Api
participant "Fila Azure" as Azure
participant "Api Externa" as Externa
participant "Dados Coala" as Banco

Totem -> Api ++ : /api2/Sync/PostSectorClothing
Api -> Azure ++ : Coalabus/Eventotagcliente
Azure -> Externa ++: /api/Tags/eventotagclienteconsumer
Externa -> Banco ++: Insere na dbo.TAGSEVENTOCLIENTE
Externa <-- Banco --: Gabriel Teste
Azure <-- Externa --: Gabriel Teste
@enduml

