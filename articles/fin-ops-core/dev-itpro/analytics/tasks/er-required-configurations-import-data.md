---
title: ER Skapa erforderliga konfigurationer för att importera data från en extern fil
description: Det här avsnittet beskriver hur du designar ER-konfigurationer för elektronisk rapportering som importerar data till Microsoft Dynamics 365 Finance-appen från en extern fil.
author: NickSelin
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERSolutionCreateDropDialog, EROperationDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula, Tax1099Summary, VendSettlementTax1099
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7eaa35baae8e030d8a8b7ce903554c4876c874b48cfd72d6ac278cf4c0e8a6e8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720866"
---
# <a name="er-create-required-configurations-to-import-data-from-an-external-file"></a>ER Skapa erforderliga konfigurationer för att importera data från en extern fil

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare som har rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan designa konfigurationer för Elektronisk rapportering (ER) så att dessa importerar data till programmet från en extern fil. I det här exemplet skapar du de ER-konfigurationer som krävs för exempelföretaget Litware, Inc. För att slutföra stegen måste du först slutföra stegen i uppgiftsguiden ”ER skapa en konfigurationsleverantör” och markera den som aktiv." Stegen kan utföras med hjälp av datauppsättningen USMF. Du måste också hämta följande filer och lagra dem lokalt: 

| Beskrivning av innehåll                       | Filnamn                                     |
|-------------------------------------------|-----------------------------------------------|
| Konfiguration av ER-datamodell - 1099 | [1099model,xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)                  |
| Konfiguration för ER-fomat - 1099    | [1099format.xml](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)                  |
| Exempel på inkommande dokument i XML-format                          | [1099entries.xml](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)        |
| Exempel på arbetsboken för att hantera data för inkommande dokument                          | [1099entries.xlsx](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx) |

ER ger företagsanvändare möjlighet att konfigurera importen av externa datafiler till tabeller i antingen XML- eller TXT-format. Först måste en abstrakt datamodell och en konfiguration av en ER-datamodell skapas med syfte att representera de data som du importerar. Därefter måste du definiera strukturen för den fil som du importerar och den metod som du använder för att porta datan från filen till den abstrakta datamodellen. ER-formatkonfigurationen som mappar till utformad datamodell måste skapas för den abstrakta datamodellen. Därefter måste modellkonfiguration utökas med en mappning som beskriver hur den importerade datan bevaras som data för en abstrakt datamodell, samt hur den används för att uppdatera tabellerna.  Modellkonfigurationen för ER-data måste läggas till en ny modellmappning som beskriver hur datamodellen är kopplad till programmodellens mål.  

I följande scenario visas importmöjligheterna för ER-dataimport. Detta inkluderar leverantörstransaktioner som spåras externt och sedan importeras för att senare rapporteras i leverantörskvittningen för 1099-rapportering.   

## <a name="add-a-new-er-model-configuration"></a>Lägg till en ny konfiguration för ER-modell
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.

    Kontrollera att konfigurationsleverantören för exempelföretaget Litware, Inc. är tillgängligt och markerats som aktivt. Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.   

2. Klicka på Reporting configurations.

    Ladda filen 1099model.xml som du tidigare hämtade, istället för att skapa en ny modell för dataimporten. Filen innehåller den anpassade datamodellen för leverantörtransaktioner. Denna datamodell mappas till de datakomponenter som finns i dataenheten AOT.   

3. Klicka på Byt.
4. Klicka på Läs in från XML-fil.

    Klicka på Bläddra och navigera till filen 1099model.xml som du hämtade tidigare.  

5. Klicka på OK.
6. Välj "Betalningsmodell 1099" i trädet.

## <a name="review-data-model-settings"></a>Granska inställningar för datamodell
1. Klicka på Designer.

    Denna modell har utformats för att representera leverantörstransaktioner från företagets synvinkel, och är åtskilda från implementeringen.   

2. Expandera "1099-MISC" i trädet.
3. Välj "1099-MISC\Transactions" i trädet.
4. Expandera "1099-MISC\Transactions" i trädet.

    Elementet Transaktioner i denna modell representerar enskilda transaktioner. De underordnade elementen används för att ange obligatorisk information, till exempel leverantörens konto och datum för varje transaktion.   

5. Stäng sidan.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Lägg till en ny konfiguration för ER-format som stöder import av data
Stegen i den här underaktiviteten visar hur en ny konfiguration av formatet kan skapas som hanterar importen av data från externa filer.   
1. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
2. Ange "Format som baseras på datamodellen Betalningsmodell 1099" i fältet Ny.
3. Välj Ja i fältet Stöder dataimport.
4. Tryck på ESC för att stänga den här sidan.

    Ladda filen 1099model.xml som du tidigare hämtade, istället för att skapa ett nytt format för dataimporten. Denna fil innehåller angiven struktur i den fil som du importerar, samt mappningen av strukturen till leverantörstransaktionernas anpassade datamodell.   
5. Klicka på Byt.
6. Klicka på Läs in från XML-fil.
    Klicka på Bläddra och navigera till filen 1099format.xml som du hämtade tidigare.  
7. Klicka på OK.
8. Expandera "Betalningsmodell 1099" i trädet.
9. Välj transaktionerna "1099 Payments model\Format for importing vendors" i trädet.

## <a name="review-format-settings"></a>Granska formatinställningar
1. Klicka på Designer.
2. Ange "Visa detaljerad information" som PÅ.
3. Klicka på Expandera/Komprimera.
4. Klicka på Expandera/Komprimera.

    Det utformade formatet representerar den externa filens förväntade struktur. Denna fil måste vara i XML-format och ha rotelementet för kvittning. Varje leverantörstransaktion representeras av det transaktionselement som har formaterats med multipliciteten noll-till-många. Detta innebär att den importerade filen kan innehålla någonstans från noll till flera transaktioner. Kapslade element i elementet "transaktion" representerar attribut för en enda transaktion. Observera att alla attribut (utom landet) markeras som obligatoriska, vilket innebär att måste finnas med i importfilen.   

## <a name="review-the-settings-of-the-format-mapping-to-the-data-model"></a>Kontrollera inställningarna för formatmappningen till datamodellen
1. Klicka på Mappa format till modell.

    Mappningen "För att importera leverantörers transaktioner" innehåller dataöverföringsreglerna från den importerade XML-filen till den anpassade datamodellen, som definieras genom att markera definitionen 1099-MISC.  

2. Klicka på Designer.
3. Ange "Visa detaljerad information" som PÅ.
4. Expandera "format: Post" i trädet.
5. Välj "format: Post" i trädet.

    Observera att det utformade formatet här presenteras som en datakällekomponent.  

6. Expandera `format: Record\*settlement: XML Element 1..1 (settlement): Record` i trädet.
7. Expandera `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list` i trädet.
8. Expandera `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record` i trädet.
9. Expandera `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\country: XML Element 0..1 (country): Record` i trädet.
10. Välj `format: Record\*settlement: XML Element 1..1 (settlement): Record\transaction: XML Element 0..* (transaction): Record list\*vendor: XML Element 1..1 (vendor): Record` i trädet.

    Observera att presentationen av obligatoriska och valfria formatelement varierar i den fördefinierade datakällekomponenten "Formatera".  
11. Expandera "Transactions: Record list= format.settlement.'$enumerated'" i trädet.

    Observera att elementen i det format som definierar strukturen i den importerade filen är bundna av elementen i den anpassade datamodellen. Utifrån dessa bindningar kan innehållet i den importerade XML-filen lagras i den befintliga datamodellen vid körning. Ta hänsyn till bindningen för nationselementet. För transaktionselement i den importerade filen utan sådant element kommer standardkoden "USA" att användas i datamodellen.  

12. Klicka på fliken Valideringar.

    Denna formatmappning kan innehålla användardefinierad logik för att validera korrektheten i den importerade datan ur ett företagsperspektiv. För alla transaktioner i importfilen som saknar en angiven nationskod kommer exempelvis, beroende på inställning, ett varningsmeddelande att skapas i informationsloggen som informerar användaren om ärendet och anger transaktionens löpnummer.  

13. Stäng sidan.

## <a name="run-the-format-mapping-to-the-data-model"></a>Kör formatmappningen till datamodellen
Kör denna formatmappning i testsyfte. Använd filen 1099entries.xml som du tidigare hämtade. Du kan exportera denna fil från arbetsboken 1099entries.xlsx, som används för att hantera leverantörstransaktioner. Skapade utdata kommer att importeras från den valda XML-filen och anges i den anpassade datamodellen när den verkliga importen sker.  

1. Klicka på Kör.

    Klicka på Bläddra och navigera till filen 1099entries.xml som du hämtade tidigare.  

2. Klicka på OK.

    Observera varningsmeddelandet om en saknad landskod för en transaktion i den importerade filen.  
    
    Granska utdata i XML-format, vilket representerar de data som har importerats från den valda filen och integrerats i datamodellen.   

3. Stäng sidan.
4. Stäng sidan.

## <a name="review-the-settings-for-the-model-mapping-to-the-destinations"></a>Kontrollera inställningarna för modellmappningen till målen
1. Välj "Betalningsmodell 1099" i trädet.
2. Klicka på Designer.
3. Klicka på Mappa modell till datakälla.

    Mappningen för manuella 1099-transaktioner har definierats med målriktningstypen Till. Detta innebär att den har angetts för dataimport och innehåller inställningen av de regler som definierar hur extern fil importeras och sparas när data för abstrakt datamodell används för att uppdatera tabeller i programmet.  

4. Klicka på Designer.
5. Expandera "model: Data model 1099 Payments model" i trädet.
6. Expandera "model: Data model 1099 Payments model\Transactions: Record list" i trädet.

    Observera att den utformade modellen här presenteras som ett datakällselement. Vid körningen kommer den att innehålla de data som importeras från den externa filen. Flera tabeller har lagts till som datakällelement i syfte att säkerställa att importerade data är kompatibla med uppgifterna i det aktuella programmet, bland annat huruvida kontot för den importerande transaktionsleverantören är tillgängligt i systemet, om kombinationen av importerade lands- och delstatskoder finns osv.  

7. Välj model: Data model 1099 Payments model\Transactions: Record list\$failed: Calculated field = IF(OR(ISEMPTY(model.Transactions.'$refs'.vendor), ISEMPTY(model.Transactions.'$refs'.vendor1099), ISEMPTY(model.Transactions.'$refs'.box1099), ISEMPTY(model.Transactions.'$refs'.country), ISEMPTY(model.Transactions.'$refs'.state), ISEMPTY(model.Transactions.'$refs'.location)), true, false): Boolean i trädet.
8. Klicka på Redigera.
9. Klicka på Redigera formel.

    När minst en validering misslyckas för en enskild importerad transaktion, kommer datakällattributet "$failed" att markera denna transaktion som misslyckad.  

10. Stäng sidan.
11. Klicka på Avbryt.
12. Välj "tax1099trans: Table 'VendSettlementTax1099' records= model.Validated" i trädet.
13. Klicka på Redigera mål.

    Detta ER-mål lades till i syfte att ange hur den importerade informationen uppdaterar programtabellerna. I det här fallet har tabellen VendSettlementTax1099 valts. Eftersom du har valt poståtgärden Infoga kommer importerade transaktioner att infogas i tabellen VendSettlementTax1099. Observera att en enskild modellmappning kan innehålla flera mål. Detta innebär att den importerade informationen kan användas för att uppdatera tabeller i flera program samtidigt. Tabeller, vyer och dataenheter kan användas som mål för ER.   

    Om mappningen anropas från en punkt i programmet (t.ex. en knapp eller ett menyobjekt) som är särskilt utformat för denna åtgärd, ska ER-målet markeras som integreringspunkt. I det här exemplet är detta punkten ERTablemål#VendSettlementTax1099.  

14. Klicka på Avbryt.
15. Klicka på Visa alla.
16. Klicka på Visa endast mappade.
17. Expandera "tax1099trans: Table 'VendSettlementTax1099' records= model.Validated" i trädet.

    Observera att det datakällelement som innehåller de enda validerade transaktionerna binds till det skapade målet. Du kan filtrera transaktionerna som importerats för att hoppa över dem som är inkompatibla med datan i programmen.  

18. Välj "failed: Table 'VendSettlementTax1099Entity' records= model.Failed" i trädet.
19. Klicka på fliken Valideringar.

    Denna modellmappning kan innehålla användardefinierad logik för att validera korrektheten i den importerade datan från den befintliga programdatan. Baserat på nuvarande inställning kommer exempelvis, för alla transaktioner i importfilen med ett leverantörskonto som inte finns i systemet, ett varningsmeddelande att skapas som informerar användaren om ärendet och anger den felaktiga leverantörskontokoden.  

    Observera att alternativet Bokför valideringsåtgärd kan användas för varje godkännande, detta för att ange om importprocessen måste fortsätta eller stoppas, samt om redan utförda infogningar/uppdateringar kan sparas eller återställas.  

20. Klicka på Visa endast mappade.
21. Klicka på Visa alla.
22. Stäng sidan.

    Kör den här modellmappningen för att testa designade format och modellmappningar. Använd filen 1099entries.xml. Datan från den valda filen importeras i systemet.  

23. Klicka på Kör.

    Observera att dialogrutan inte innehåller några ytterligare frågor om den formatmappning som ska användas för att tolka den importerade filen och porta datan till datamodellen. Detta beror på att det för tillfället finns endast ett format som använder denna modell, markerat som utformat att stödja dataimport.  
    
    Definiera kupong-ID för att skilja de importerade transaktionerna från andra transaktioner som redan har matats in manuellt eller importerats.  

24. Ange "IMPORT-001" i fältet Ange kupong-ID.

    Bläddra för att hämta filen "1099entries.xml".  

25. Klicka på OK.

    Lista över skapade varningar innehåller information om fel leverantörskonton, en felaktig en rutkod för felaktig 1099-skatt, saknade landskoder osv. Jämför listan med varningar till det innehåll som ingår i körning av XML-filen.  

26. Stäng sidan.
27. Stäng sidan.
28. Stäng sidan.
29. Stäng sidan.
30. Gå till Leverantörsreskontra > Periodiska uppgifter > 1099-skatt > Leverantörskvittning för 1099-rapportering.

    Detta formulär visar ackumulerade transaktioner i tabellen Tax1099Summary, som har skapats baserat på importerade transaktioner.  

31. Ange datumet till "2000-01-01" i fältet Från datum.
32. Klicka på Manuella 1099-transaktioner.

    Det här formuläret innehåller en lista över transaktioner som har lagts till manuellt och sådana som vi just har importerat.  

33. Öppna Kolumnfilter för kupong.
34. Ange filtervärdet "IMPORT-001" i fältet "Kupong" med hjälp av filteroperatören "börjar med".

## <a name="review-the-relationship-between-model-and-format-mappings"></a>Granska förhållandet mellan modell- och formatmappningar
1. Stäng sidan.
2. Stäng sidan.
3. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
4. Klicka på Reporting configurations.
5. Välj "Betalningsmodell 1099" i trädet.

    Anta att du vill kunna importera samma data, men från ett .TXT-filformat.   

6. Klicka på Skapa konfiguration om du vill öppna dialogrutan. 
7. Ange "Format som baseras på datamodellen Betalningsmodell 1099" i fältet Ny.
8. Ange "Importera data från TXT-fil" i namnfältet.
9. Välj Ja i fältet Stöder dataimport.
10. Klicka på Skapa konfiguration.
11. Klicka på Designer.
12. Klicka på Mappa format till modell.
13. Klicka på Ny.
14. Ange eller välj ett värde i fältet Definition.

    Välj alternativet "1099-MISC".  

15. Ange "Importera data från TXT-fil" i namnfältet.
16. Ange "Importera data från TXT-fil" i fältet Beskrivning.
17. Klicka på Spara.
18. Stäng sidan.
19. Stäng sidan.
20. Klicka på Redigera.

    Om du har installerat snabbkorrigeringen "KB 4012871 Stöd för TYS modellmappningar i separata konfigurationer med möjlighet att ange olika typer av krav vid tillämpning av dem i olika versioner av Dynamics 365 Finance" ([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871)) kör då nästa steg "Aktivera flaggan Standard för modellmappning" för angiven formatkonfiguration. Hoppa annars över nästa steg.  

21. Välj Ja i fältet Standard för modellmappning.
22. Välj "Betalningsmodell 1099" i trädet.
23. Klicka på Designer.
24. Klicka på Mappa modell till datakälla.
25. Klicka på Kör.

    Om du har installerat snabbkorrigeringen "KB 4012871 Stöd för TYS modellmappningar i separata konfigurationer med möjlighet att ange olika typer av krav vid tillämpning av dem i olika versioner av ([KB 4012871](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871)) ska du välja föredragen modellmappning i sökfältet. Om du ännu inte har installerat snabbkorrigeringen än, hoppa då vidare till nästa steg eftersom det förvalda formatets konfigurationsdefinition redan har valt mappningen.  
    
    Om du inte har installerat snabbkorrigeringen KB 4012871, observera då att dialogrutan innehåller en ytterligare modellmappningsfråga som används för att tolka den fil som du importerar. Datan postas sedan från dialogrutan till datamodellen. För närvarande kan du välja vilken formatmappning som måste användas beroende på den typ av fil som du tänker importera.  
    
    Om du planerar att anropa den här modellmappningen från en punkt i programmet som har utformats speciellt för åtgärden, måste ER-målet och formatmappningen markeras som en del av integreringen.  

26. Klicka på Avbryt.
27. Stäng sidan.
28. Stäng sidan.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
