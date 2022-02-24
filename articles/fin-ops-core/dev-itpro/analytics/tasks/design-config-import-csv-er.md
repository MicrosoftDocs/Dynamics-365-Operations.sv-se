---
title: Utforma ER-konfigurationer för att importera data från externa CSV-filer
description: Använd den här guiden för att designa ER-konfigurationer för elektronisk rapportering som importerar data till programmet Finance and Operations från en extern fil i CSV-format.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b542b6250bcc72334659e050f7ab6d5bd87d3508
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682055"
---
# <a name="design-er-configurations-to-import-data-from-external-csv-files"></a>Utforma ER-konfigurationer för att importera data från externa CSV-filer

[!include [banner](../../includes/banner.md)]

Använd den här guiden för att designa ER-konfigurationer för elektronisk rapportering som importerar data till programmet från en extern fil i CSV-format. I den här proceduren skapar du de ER-konfigurationer som krävs för exempelföretaget Litware, Inc. För att slutföra stegen måste du först slutföra stegen i proceduren ”ER skapa en konfigurationsleverantör” och markera den som aktiv.

Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av datauppsättningen USMF.

Du måste också hämta och spara följande filer lokalt: [Dynamics 365 Finance exempel på elektronisk rapportering](https://go.microsoft.com/fwlink/?linkid=862266): 1099model.xml, 1099formatcsv.xml, 1099entriescsv.csv.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Du kan konfigurera en process för att importera externa filer i XML-, CSV- eller TXT-format till register i programmet . Först måste du skapa en abstrakt datamodell för att representera importerade data från affärssynpunkt – en konfiguration av ER-datamodell skapas för den. Härnäst definiera en struktur av den importerade filen som mappas till den utformade datamodellen för att bära data från filen till den abstrakt datamodellen – en ER-formatkonfiguration skapas för den importerade filen. Därefter måste ER-modellkonfiguration utökas med en ny modellmappning som beskriver hur data från den importerade filen bevaras som data för en abstrakt datamodell, samt hur den används för att uppdatera programtabellerna eller dataenheterna.
    * I följande steg visas hur externt spårade leverantörers transaktioner importeras från extern CSV-fil för senare användning i leverantörskvittning för 1099-rapportering.
    * Kontrollera att konfigurationsleverantören för provföretaget Litware, Inc. är markerad som aktiv och tillgänglig. Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.
2. Klicka på Reporting configurations.
3. Tillämpa filtret Betalningsmodell 1099. Om du redan har slutförts proceduren ”ER Skapa erforderliga konfigurationer för att importera data från en extern fil för elektronisk rapportering” och konfigurationen ”1099 betalningsmodell" finns i konfigurationsträdet, hoppa över alla stegen i nästa underaktivitet.

## <a name="add-a-new-er-model-configuration"></a>Lägg till en ny konfiguration för ER-modell

1. Ladda filen 1099model.xml som du tidigare hämtade, istället för att skapa en ny modell för dataimporten. Filen innehåller den anpassade datamodellen för leverantörtransaktioner. Denna datamodell är redan mappad till nödvändiga komponenter.
2. Klicka på Byt.
3. Klicka på Läs in från XML-fil.
4. Klicka på Bläddra och navigera till filen 1099model.xml som du hämtade tidigare.
5. Klicka på OK.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Lägg till en ny konfiguration för ER-format som stöder import av data

1. Välj "Betalningsmodell 1099" i trädet.
2. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
3. Ange "Format som baseras på datamodellen Betalningsmodell 1099" i fältet Ny.
4. Välj Ja i fältet Stöder dataimport.
5. Tryck på ESC för att stänga den här sidan.
    * Ladda filen 1099formatcsv.xml som du tidigare hämtade, istället för att skapa ett nytt ER-format för dataimporten. Denna fil innehåller krävt ER-format som definierar strukturen för inkommande CVS-fil och mappning av denna struktur till leverantörstransaktionernas anpassade datamodell.
6. Klicka på Byt.
7. Klicka på Läs in från XML-fil.
    * Klicka på Bläddra och navigera till filen 1099formatcsv.xml som du hämtade tidigare.
8. Klicka på OK.
9. Expandera "Betalningsmodell 1099" i trädet.
10. Välj "1099 Payments model\For importing vendors' transactions (CSV)" i trädet.

## <a name="review-format-settings"></a>Granska formatinställningar

1. Klicka på Designer.
2. Klicka på Expandera/Komprimera.
3. Ange "Visa detaljerad information" som PÅ.
    * Det utformade formatet representerar den externa filens förväntade struktur i CVS-format.
4. Välj "Incoming: File\Root: Sequence" i trädet.
    * För Root-elementet av typen SEQUENCE har alternativet "Ny rad - Windows (CR LF)" valts i fältet "Specialtecken". Utifrån den här inställningen beaktas varje rad i parsingfilen som en separat post.
5. Välj `Incoming: File\Root: Sequence\Line: Sequence 1..*` i trädet.
    * För elementen Root\Line av typen SEQUENCE, måste alternativet "Ett många" ha valts i fältet "Sammansatt". Baserat på denna inställning visas på minst en rad i parsingfilen.
6. Välj `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case` i trädet.
    * Observera att elementen Root\Line\Types av typen CASE har lagts till som det kapslade elementet i Root\Line sequence. Eftersom det här CASE-elementet innehåller 3 kapslade sekvenselement, förutsätter inställningen att vi förväntar oss att uppfylla 3 olika typer av rad i parsingfilen.
7. Välj `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Header: Sequence 1..1` i trädet.
    * Element Root\Line\Types\Header av typen SEQUENCE innehåller kapslade STRING-element vars värde har definierats som fasta strängvärdet. Den här sekvensen kan tolka rubrikraden i parsingfilen.
8. Välj `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)` i trädet.
    * Elementen Root\Line\Types\Record av typen SEQUENCE, har konfigurerats för att parsa transaktionsraderna. Observera att teckenalternativet Anpassad avgränsare har konfigurerats som ett komma. Detta innebär att ett kommatecken används som avgränsare i ett fält för den här raden i parsingfilen.
    * Lägg märke till att flera kapslade element av olika datatyper har lagts till för elementet Root\Line\Types\Record för parsing av transaktionsrader som avgränsade fält. Observera att alternativet ”Offertprogram” har konfigurerats som "Inget". Detta innebär att alla fält av den här typen i parsingfilen ska betraktas som det inte har några bifogade tecken.
9. Välj `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\TransactionDate: DateTime` i trädet.
    * Exempelvis elementen Root\Line\Types\Record\TransactionDate av typen DATETIME har konfigurerats för att få transaktionens datum och tid från parsingfilen i formatet M/d/åååå.
10. Välj `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\CountryCode: String 0..1` i trädet.
    * Observera att alementet Root\Line\Types\Record\CountryCode av typen STRING har konfigurerats med alternativet Noll ett i fältet "Sammansatt". Den här inställningen anser värdet av CountryCode-fältet i analyseringsraden som valfritt.
11. Välj `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Record: Sequence 1..1 (,)\Remark: Sequence 1..1 (,)` i trädet.
    * Observera att elementet Root\Line\Types\Record\Remark av typen SEQUENCE har konfigurerats som tecken i fältet citattecken med alternativet ”alla” i fältet ”Offertprogram” i dubbla citattecken. Detta innebär att alla fält av den här typen av rader i parsingfilen (beskrivs i kapslade element: Text av typen STRING) betraktas omgiven av dubbelt citattecken.
12. Välj `Incoming: File\Root: Sequence\Line: Sequence 1..* \Types: Case\Unparsed: Sequence 1..1` i trädet.
    * Elementen Root\Line\Types\Unparsed av typen SEQUENCE har konfigurerats så för att tolka transaktionsrader för strukturen som inte matchar den struktur som beskrivs ovan i det överordnade elementet CASE.

## <a name="review-the-setting-of-the-format-mapping-to-the-data-model"></a>Kontrollera inställningarna för formatmappningen till datamodellen

1. Klicka på Mappa format till modell.
    * Modellmappning ”mappa till modell från CSV-format" beskriver dataflödet för dataöverföringen från den inkommande CSV-filen till datamodellen.
2. Klicka på Designer.
3. Expandera format i trädet.
    * Observera att det utformade formatet här presenteras som en datakällekomponent.
4. Expandera "format\Incoming: File(Incoming)" i trädet.
5. Expandera "format\Incoming: File(Incoming)\Root: Sequence(Root)" i trädet.
6. Expandera `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)` i trädet.
7. Expandera `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)` i trädet.
8. Expandera `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)` i trädet.
9. Expandera `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data` i trädet.
10. Expandera `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data\CountryCode: String 0..1 (CountryCode)` i trädet.
11. Välj `format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data\TransactionDate: DateTime(TransactionDate)` i trädet.
    * Observera att obligatoriska och valfria formatetelement, till exempel TransactionDate och CountryCode, ser annorlunda ut i komponenten fördefinierat format datakälla.
12. Expandera Transactions= = '$both''.
    * Observera att elementen i det format som definierar strukturen i den importerade filen är bundna av elementen i datamodellen. Utifrån dessa bindningar kan innehållet i den importerade CSV-filen lagras i den befintliga datamodellen vid körning. Ta hänsyn till bindningen för nations/regions-elementet. För transaktionselement i den importerade filen utan specificerad landskod kommer standardkoden "USA" att användas i datamodellen.
13. Ange "Visa detaljerad information" som PÅ.
14. Klicka på fliken Valideringar.
15. Klicka på Sök.
16. Ange "Vend" i fältet Sök.
17. Klicka på Sök nästa.
    * Denna formatmappning kan innehålla användardefinierad logik för att validera korrektheten i den importerade datan ur ett företagsperspektiv. Till exempel, baserat på inställningen, för varje rad i importfilen, vars struktur inte matchar varken strukturen hos rubriklinjen eller transaktionslinjen, kommer ett varningsmeddelande att skapas i infologgen för att informera användaren om detta fall, vilket indikerar transaktionens sekvensnummer i filen.
18. Stäng sidan.

## <a name="run-the-format-mapping"></a>Kör mappning av filformat

För testningsändamål, utför formatmappning med den 1099entriescsv.csv-fil som du tidigare hämtade. Skapade utdata kommer att presentera data som importeras från den valda CSV-filen och fyller i den anpassade datamodellen när den verkliga importen sker.

1. Klicka på Kör.
    * Klicka på Bläddra och navigera till filen 1099entriescsv.csv som du hämtade tidigare.
2. Klicka på OK.
    * Observera att varningsmeddelanden om rader som inte är tillåtna. Rad 4 innehåller inkomstvärdet som presenteras i det icke godtagbara formatet medan rad 7 inte innehåller transaktionskommentartexten inom dubbla citattecken.
    * Granska utdata i XML-format, vilket representerar de data som har importerats från den valda filen och integrerats i datamodellen. Observera att alla 7 raderna i importerade CSV-filen har bearbetats. Det innehållande fältets rubrikrad 1 hoppades över, 4 transaktioner analyserades korrekt och 2 transaktioner erkändes som otillåtna.
3. Stäng sidan.
4. Stäng sidan.
