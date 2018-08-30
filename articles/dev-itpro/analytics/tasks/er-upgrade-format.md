--- 
title: Uppgradera format genom att implementera nya basversioner
description: "I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan behålla en formatkonfiguration för elektronisk rapportering (ER)."
author: NickSelin
manager: AnnBe
ms.date: 02/06/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 7a14299c3bdcc33a4441d1cc096b198af4d4ae4c
ms.contentlocale: sv-se
ms.lasthandoff: 08/09/2018

---
# <a name="upgrade-formats-by-adopting-new-base-versions"></a>Uppgradera format genom att implementera nya basversioner

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan behålla en formatkonfiguration för elektronisk rapportering (ER). I den här proceduren förklaras hur en anpassad version av ett format kan skapas baserat på det format som tas emot från en konfigurationsleverantör (CP). Den förklarar också hur du antar en ny basversion av det formatet.



För att slutföra dessa steg måste du först avsluta stegen i procedurerna ”Skapa en konfigurationsleverantör och markera den som aktiv" och "Använd skapade format för att skapa elektroniska handlingar för betalningar". Dessa steg kan utföras i GBSI-företaget.


## <a name="select-format-configuration-for-customization"></a>Välj formatkonfigurationen för anpassning
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * I det här exemplet kommer exempelföretaget Litware, Inc. (`http://www.litware.com`) att fungera som en konfigurationsleverantör som stöder formatkonfigurationer för elektroniska betalningar för ett angivet land.  Eexempelföretaget Proseware, Inc. (`http://www.proseware.com`) kommer att fungera som en konsument av formatkonfigurationen som Litware, Inc. tillhandahåller. Proseware, Inc. använder format i vissa regioner för det landet.  
2. Klicka på Reporting configurations.
3. Klicka på Visa filter.
4. Använd följande filter: Ange filtervärdet "BACS (fiktivt, Storbritannien)" i fältet "Namn" med hjälp av filteroperatorn "Börjar med"
    * BACS (fiktivt UK)  
    * Den valda formatkonfigurationen BACS (fiktiv, från Storbritannien) ägs av leverantören Litware, Inc.  
5. Klicka på Visa filter.
6. Hitta och markera önskad post i listan.
    * Versionen av formatet med statusen avslutad ska användas av Proseware, Inc. för anpassning.  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a>Skapa en ny konfiguration för ditt anpassade format för elektroniskt dokument
Proseware, Inc. tog emot version 1.1 av BACS-konfigurationen (fiktiv från Storbritannien) som innehåller det initiala formatet för att skapa elektroniska betalningsdokument från Litware, Inc. i enlighet med deras serviceabonnemang. Proseware, Inc. vill börja använda detta som standard för deras land, men det krävs en del anpassning för att stödja specifika regionala krav. Proseware, Inc. vill behålla förmågan att uppgradera ett allmänt format så snart som en ny version av den (med ändringar som stöder nya landsspecifika behov) kommer från Litware, Inc. och de vill utföra denna uppgradering med den lägsta kostnaden.  För att göra detta måste Prosewares, Inc. skapa en konfiguration med Litware Inc. konfiguration BACS (fiktiva UK) som bas.  
1. Stäng sidan.
2. Välj Prosewares Inc. för att göra den till en aktiv leverantör.
3. Klicka på Ställ in aktiv.
4. Klicka på Reporting configurations.
5. Visa "Betalningar (förenklad modell)" i trädet.
6. Välj "Betalningar (förenklad modell)\BACS (UK fiktivt)" i trädet.
    * Välj konfigurationen (fiktiva UK) från Litware, Inc. Prosewares Inc. kommer att använda 1.1 som bas för din anpassade version.  
7. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
    * Detta låter dig skapa en ny konfiguration för ett anpassat betalningsformat.  
8. Ange ”Härled från namn: BACS (UK fiktivt) Litware, Inc.” i fältet Nytt.
    * Välj alternativet Härled för att bekräfta användningen av BACS (fiktivt UK) som bas för att skapa den anpassade versionen.  
9. Skriv "BACS (fiktiv UK kund) i fältet Namn.
    * BACS (fiktiv kund från Storbritannien)  
10. Skriv "BACS-leverantörsbetalnings (fiktivt, Storbritannien)" i fältet Beskrivning.
    * BACS-leverantörsbetalning (fiktiv, anpassad från Storbritannien)  
    * Den aktiva konfigurationsleverantören (Proseware, Inc.) anges automatiskt här. Den här leverantören kommer att kunna underhålla konfigurationen. Andra leverantörer kan använda den här konfigurationen, men de kan inte underhålla den.  
11. Klicka på Skapa konfiguration.

## <a name="customize-your-format-for-the-electronic-document"></a>Anpassa ditt format för elektroniskt dokument
1. Klicka på Designer.
2. Klicka på Expandera/Komprimera.
3. Klicka på Expandera/Komprimera.
4. Välj "Xml\Message\Payments\Item\Vendor\Bank" i trädet.
5. Klicka på Lägg till för att öppna dialogrutan.
6. Välj "XML\Element" i trädet.
7. Skriv "IBAN" i fältet Namn.
    * IBAN  
8. Klicka på OK.
9. Välj "Xml\Message\Payments\Item\Vendor\Bank\IBAN" i trädet.
10. Klicka på Lägg till för att öppna dialogrutan.
11. Välj "Text\Sträng" i trädet.
12. Klicka på OK.
13. Välj "Xml\Message\Payments\Item\Vendor\Name\String" i trädet.
14. Ange "60" i fältet Maximal längd.
15. Klicka på fliken Mappning.
16. Expandera "modell" i trädet.
17. Expandera "modell\Betalningar" i trädet.
18. Expandera "modell\Betalningar\Betalningsmottagare" i trädet.
19. Expandera "modell\Betalningar\Betalningsmottagare\Konto" i trädet.
20. Välj "model\Payments\Creditor\Account\IBAN" i trädet.
21. Välj "Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\IBAN\String" i trädet.
22. Klicka på Bind.
23. Klicka på Spara.

## <a name="validate-the-customized-format"></a>Validera det anpassade formatet
1. Klicka på Validera.
    * Validera det anpassade formatlayoutet och datamappningändringarna för att se till att alla bindningar är ok.  
2. Stäng sidan.

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a>Ändra statusen för den aktuella versionen av den anpassade formatkonfigurationen
    * Ändra statusen för den utformade formatkonfigurationen från Utkast till Slutfört för att göra den tillgänglig för generering av betalningsdokument.  
1. Klicka på Ändra status.
    * Observera att den aktuella versionen av den valda konfigurationen finns i utkastläge.  
2. Klicka på Slutför.
3. Ange ett värde i fältet Beskrivning.
4. Klicka på OK.
5. Hitta och markera önskad post i listan.
    * Observera att den skapade konfigurationen sparas som slutförd version 1.1.1. Det innebär att det är version 1 av det anpassade BACS-formatet (fiktiv kund från Storbritannien) baserat på version 1 av BACS-formatet (fiktiv från Storbritannien) baserat på version 1 av datamodellen Betalningar (förenklad modell).  

## <a name="test-the-customized-format-to-generate-payment-files"></a>Testa det anpassade formatet för att skapa betalningsfiler
Slutför stegen i sessionen "Använd skapade format för att skapa elektroniska dokument för betalningar" i en parallell session för Dynamics 365 for Finance and Operations. Välj det BACS-formatet (fiktiv kund från Storbritannien) i parametrar för elektronisk betalningsmetod. Kontrollera att den skapade betalningsfilen innehåller den för en tid eftersom introducerade XML-noden som innehåller IBANkod i korrespondens till regionala kraven.  

## <a name="update-the-existing-country-specific-configuration"></a>Uppdatera den befintliga landsspecifika konfigurationen
Litware, Inc. behöver uppdatera BACS-konfigurationen (fiktivt UK) och anta nya landskrav för hantering av formatet för elektroniskt dokument. Senare kommer detta att bifogas i en ny version av den här konfigurationen som ska erbjudas abonnenter, inklusive Proseware, Inc.  

I verkliga tjänsterelaterade processer kan varje ny version av BACS (fiktiv från Storbritannien) importeras av Proseware, Inc. från Litware, Inc. konfigurationers LCS-databas. I den här proceduren kommer vi att simulera detta genom att uppdatera BACS (fiktiv från Storbritannien) på uppdrag av en tjänsteleverantör.

1. Stäng sidan.
2. Välj leverantören Litware, inc.
3. Klicka på Ställ in aktiv.
4. Klicka på Reporting configurations.
5. Visa "Betalningar (förenklad modell)" i trädet.
6. Välj "Betalningar (förenklad modell)\BACS (UK fiktivt)" i trädet.
    * Utkastversionen som ägs av Litware, Inc. leverantören BACS (fiktivt UK) för att ta in ändringar som stödjer nya landsspecifika krav.  

## <a name="localize-the-base-format-of-the-electronic-document"></a>Lokalisera basformat för elektroniskt dokument
Anta att det finns nya landsspecifika krav som stöds av Litware, Inc.:  
- Ett värde för betalningsmottagarens SWFT-kod i varje betalningstransaktion.  
- En gräns på 100 tecken för textlängden för leverantörens namn i en genereringsfil.  
 
Välj utkastversionen av önskad konfiguration för att införa nödvändiga ändringar.  

1. Klicka på Designer.
2. Klicka på Expandera/Komprimera.
3. Klicka på Expandera/Komprimera.
4. Välj "Xml\Message\Payments\Item\Vendor\Bank" i trädet.
5. Klicka på Lägg till för att öppna dialogrutan.
6. Välj "XML\Element" i trädet.
7. Skriv "SWIFT" i fältet Namn.
    * SWIFT  
8. Klicka på OK.
9. Välj "Xml\Message\Payments\Item\Vendor\Bank\SWIFT" i trädet.
10. Klicka på Lägg till för att öppna dialogrutan.
11. Välj "Text\Sträng" i trädet.
12. Klicka på OK.
13. Välj "Xml\Message\Payments\Item\Vendor\Name\String" i trädet.
14. Ange "100" i fältet Maximal längd.
15. Klicka på fliken Mappning.
16. Expandera "modell" i trädet.
17. Expandera "modell\Betalningar" i trädet.
18. Expandera "modell\Betalningar\Betalningsmottagare" i trädet.
19. Expandera "modell\Betalningar\Betalningsmottagare\Agent" i trädet.
20. Välj "model\Payments\Creditor\Agent\SWIFT" i trädet.
21. Välj "Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\SWIFT\String" i trädet.
22. Klicka på Bind.
23. Klicka på Spara.

## <a name="validate-the-localized-format"></a>Validera det lokaliserade formatet
1. Klicka på Validera.
2. Stäng sidan.

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a>Ändra statusen för den aktuella versionen av basformatkonfigurationen
Ändra status för den uppdaterade basformatkonfigurationen från utkast till slutfört om du vill göra den tillgänglig för generering av betalningdokument och uppdatering av formatkonfigurationer som härleds från den.  
1. Klicka på Ändra status.
    * Observera att den aktuella versionen av den valda konfigurationen finns i utkastläge.  
2. Klicka på Slutför.
3. Ange ett värde i fältet Beskrivning.
4. Klicka på OK.
5. Hitta och markera önskad post i listan.

## <a name="change-the-base-version-for-the-custom-format-configuration"></a>Ändra basversionen för anpassad formatkonfiguration
Proseware, Inc. informeras att en ny version 1.2 av BACS-konfigurationen (fiktivt UK) är tillgänglig om du vill skapa elektroniska betalningsdokument i enlighet med tillkännagivna landsspecifika krav. Proseware, Inc. vill börja använda den som standard för landet.  För att göra detta måste Proseware, Inc. ändra baskonfigurationversionen för den anpassade BACS-konfigurationen för (fiktiv UK kund). I stället för version 1.1 för BACS (fiktivt UK), använd version 1.2.  

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Välj Prosewares Inc. leverantör för att markera den som aktiv.
3. Klicka på Ställ in aktiv.
4. Klicka på Reporting configurations.
5. Visa "Betalningar (förenklad modell)" i trädet.
6. Expandera "Betalningar (förenklad modell)\BACS (UK fiktivt)" i trädet.
7. Välj "Betalningar (förenklad modell)\BACS (UK fiktiv kund)" i trädet.
    * Välj BACS-konfigurationen (fiktiv kund från Storbritannien), som ägs av Proseware Inc.  
    * Använd utkastversionen av den valda konfiguration för att införa nödvändiga ändringar.  
8. Klicka på Basera om.
    * Välj den nya versionen 1.2 av baskonfigurationen som ska användas som ett nytt underlag för att uppdatera konfigurationen.  
9. Klicka på OK.
    * Observera att eventuella konflikter har upptäckts mellan sammanslagning av den anpassade version och en ny basversion som representerar en del formatändringar som inte kan sammanslås automatiskt.  

## <a name="resolve-rebase-conflicts"></a>Lös basera om konflikter
1. Klicka på Designer.
    * Observera att ändringar i textlängdgränsen för leverantörens namn inte kan lösas automatiskt. Därför visas den i en konfliktlista. För varje konflikt av typen Uppdatera är följande alternativ tillgängliga: - Använd ett tidigare basvärde (knappen överst i rutnätet) om du vill ta med det föregående basversionsvärdet (0 i vårt fall).  - Använd ett basvärde (knappen överst i rutnätet) om du vill ta med det nya basversionsvärdet (100 i vårt fall).  - Behåll ditt eget (anpassade) värde (60 i det här fallet).  Klicka på Tillämpa basvärde för att använda den landsspecifika gränsen på 100 tecken för textländen på leverantörsnamnet.  
    * Observera att Proseware, Inc. och Litware, Inc. har anpassade och lokala versioner av det här formatet med hjälp av IBAN och SWIFT-koder med tillhörande komponenter som sammanslås automatiskt i det hanterade formatet.  
2. Klicka på Tillämpa innan basvärde.
    * Klicka på Tillämpa basvärde för att använda den landsspecifika gränsen på 100 tecken för leverantörsnamn.  
3. Klicka på Spara.
    * När du sparar formatet kommer lösta konflikter att tas bort från konfliktlistan.  
4. Stäng sidan.

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a>Ändra statusen för den nya versionen av den anpassade formatkonfigurationen
1. Klicka på Ändra status.
    * Ändra status för den uppdaterade anpassade formatkonfigurationen från Utkast till Slutförd. Detta kommer att göra formatkonfigurationen tillgänglig för att skapa betalningsdokument. Observera att den aktuella versionen av den valda konfigurationen finns i utkastläge.  
2. Klicka på Slutför.
3. Ange ett värde i fältet Beskrivning.
4. Klicka på OK.
    * Observera att den skapade konfigurationen sparas som slutförd version 1.2.2: version 2 av BACS-basformatet (fiktiv UK kund) baserat på version 2 av BACS-basformatet (UK fiktivt) som baseras på version 1 av datamodellen Betalningar (förenklad modell).  

## <a name="test-the-customized-format-for-payment-files-generation"></a>Testa det anpassade formatet för att skapa betalningsfiler
Slutför stegen i sessionen "Använd skapade format för att skapa elektroniska dokument för betalningar" i en parallell session för Dynamics 365 for Finance and Operations. Välj det skapade BACS-formatet (fiktiv kund från Storbritannien) i parametrar för elektronisk betalningsmetod. Kontrollera att den skapade betalningsfilen innehåller den för en tid eftersom Proseware, Inc. introducerade XML-noden som innehåller IBAN-kontokoden i korrespondens till regionala kraven. Filen ska också innehålla nyligen introducerade genom Litware Inc. XML-noden som presenterar SWIFT-bankkoden i enlighet med kraven i landet.  


