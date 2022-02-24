---
title: Skapa ER-uttryck för att anropa programklassmetoder
description: Denna guide ger information om hur du återanvänder befintlig programlogik i konfigurationer för elektronisk rapportering (ER) genom att anropa metoder för programklasser i ER-uttryck.
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
ms.openlocfilehash: 3d79d1a4e86731a62de4896a489a13f624ce159f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682031"
---
# <a name="design-er-expressions-to-call-application-class-methods"></a>Skapa ER-uttryck för att anropa programklassmetoder

[!include [banner](../../includes/banner.md)]

Denna guide ger information om hur du återanvänder befintlig programlogik i konfigurationer för elektronisk rapportering (ER) genom att anropa metoder för programklasser i ER-uttryck. Argument för att anropa klasser kan definieras dynamiskt vid körning: exempelvis utifrån information i parsningdokumentet för att säkerställa att de är korrekta. I den här handboken skapas de ER-konfigurationer som krävs för exempelföretaget Litware, Inc. Proceduren är till för användare med rollen systemadministratör eller utvecklare av elektronisk rapportering. 

Stegen kan utföras med hjälp av valfri datauppsättning. Måste du också hämta och spara följande fil lokalt: (https://go.microsoft.com/fwlink/?linkid=862266): SampleIncomingMessage.txt.

För att slutföra dessa steg måste du först slutföra stegen i proceduren "ER Skapa en konfigurationsleverantör och markera den som aktiv”.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att konfigurationsleverantören för provföretaget Litware, Inc. är markerad som aktiv och tillgänglig. Om du inte ser den här konfigurationsleverantören måste du först slutföra stegen i proceduren "Skapa en konfigurationsleverantör och välj den som aktiv”.   
    * Du du skapar en process för att parsa inkommande bankutdrag för en uppdatering av programdata. Inkommande bankutdrag visas som TXT-filer som innehåller IBAN koder. Som en del av bankutdragets importprocess behöver du kontrollera riktigheten i dessa IBAN-koder med logik som finns.   

## <a name="import-a-new-er-model-configuration"></a>Importera en ny konfiguration för ER-modell
1. Hitta och markera önskad post i listan.
    * Välj panelen Microsoft provider.  
2. Klicka på Databaser.
3. Klicka på Visa filter.
4. Lägg till ett filterfält "Typnamn". I fältet Namn anger du värdet "resurser", välj filtreringsoperatören "innehåller" och klickar sedan på Tillämpa.
5. Klicka på Öppna.
6. Välj "Betalningsmodell" i trädet.
    * Om knappen Importera på snabbfliken Versioner inte aktiveras har du redan importerat version 1 i någon av ER-konfigurationen ”betalningsmodell". Du kan hoppa över resten av stegen i den här underaktivitet.   
7. Klicka på Importera.
8. Klicka på Ja.
9. Stäng sidan.
10. Stäng sidan.

## <a name="add-a-new-er-format-configuration"></a>Lägg till en ny konfiguration för ER-format
1. Klicka på Reporting configurations.
    * Lägg till ett nytt ER-format som du vill dela upp inkommande bankutdrag i TXT-format.  
2. Välj "Betalningsmodell" i trädet.
3. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
4. Ange "Format som baseras på datamodellen PaymentModel" i fältet Ny.
5. I namnfältet anger du "bankutdragsformat för import" (exempel)
    * Importformat för bankutdrag (exempel)  
6. Välj Ja i fältet Stöder dataimport.
7. Klicka på Skapa konfiguration.

## <a name="design-the-er-format-configuration---format"></a>Designa en konfiguration för ER-format
1. Klicka på Designer.
    * Det utformade formatet representerar den externa filens förväntade struktur i TXT-format.  
2. Klicka på Lägg till rot för att öppna dialogrutan.
3. Välj "Text\Sequence" i trädet.
4. Ange "Root" i namnfältet.
    * Rot  
5. Välj "New line - Windows (CR LF)" i fältet för specialtecken.
    * Alternativet "Ny rad – Windows (CR LF)" har valts i fältet för specialtecken. Utifrån den här inställningen beaktas varje rad i parsingfilen som en separat post.  
6. Klicka på OK.
7. Klicka på Lägg till för att öppna dialogrutan.
8. Välj "Text\Sequence" i trädet.
9. Skriv "Rader" i fältet Namn.
    * Rader  
10. Välj Ett många i fältet Sammansatt.
    * Alternativet ”Ett många” har valts i fältet "Sammansatt". Baserat på denna inställning förväntas att minst en rad presenteras i parsningfilen.  
11. Klicka på OK.
12. Välj "Root\Rows" i trädet.
13. Klicka på Lägg till sekvens.
14. Skriv "Fält" i fältet Namn.
    * Fält  
15. Välj Exakt ett i fältet Sammansatt.
16. Klicka på OK.
17. Markera "Root\Rows\Fields" i trädet.
18. Klicka på Lägg till för att öppna dialogrutan.
19. Välj "Text\Sträng" i trädet.
20. Skriv "IBAN" i fältet Namn.
    * IBAN  
21. Klicka på OK.
    * Den har konfigurerats att varje rad i parsningfilen innehåller den enda IBAN-koden.  
22. Klicka på Spara.

## <a name="design-the-er-format-configuration--mapping-to-data-model"></a>Designa ER-formatkonfigurationen – mappa till datamodellen
1. Klicka på Mappa format till modell.
2. Klicka på Ny.
3. I fältet Definition anger du "BankToCustomerDebitCreditNotificationInitiation".
    * BankToCustomerDebitCreditNotificationInitiation  
4. ResolveChanges the Definition.
5. Skriv "Mappning till datamodell" i namnfältet.
    * Datamodellmappning  
6. Klicka på Spara.
7. Klicka på Designer.
8. I trädet väljer du 'Dynamics 365 for Operations\Class'.
9. Klicka på Lägg till rot.
    * Lägg till en ny datakälla för att öppna befintliga programlogik för validering av IBAN koder.  
10. Ange "Checkkoder" i namnfältet.
    * checkkoder  
11. I fältet Klass skriver du "ISO7064".
    * ISO7064  
12. Klicka på OK.
13. Expandera format i trädet.
14. Expandera "format\Root: Sequence(Root)" i trädet.
15. Välj "format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)" i trädet.
16. Klicka på Bind.
17. Expandera "format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)" i trädet.
18. Expandera "format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)" i trädet.
19. Välj "format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)" i trädet.
20. Expandera "Payments = format.Root.Rows" i trädet.
21. Expandera "Payments = format.Root.Rows\Creditor Account(CreditorAccount)" i trädet.
22. Expandera "Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification" i trädet.
23. Välj "Payments = format.Root.Rows\Creditor Account(CreditorAccount)\Identification\IBAN" i trädet.
24. Klicka på Bind.
25. Klicka på fliken Valideringar.
26. Klicka på Ny.
    * Lägg till en ny valideringsregel som visar ett felmeddelande för varje rad i filen som innehåller ogiltig IBAN-kod.  
27. Klicka på Edit condition.
28. Expandera "checkkoder" i trädet.
29. Välj "check_codes\verifyMOD1271_36" i trädet.
30. Klicka på Lägg till datakälla.
31. I formelfältet anger du "check_codes.verifyMOD1271_36(".
    * check_codes.verifyMOD1271_36(  
32. Expandera format i trädet.
33. Expandera "format\Root: Sequence(Root)" i trädet.
34. Expandera "format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)" i trädet.
35. Expandera "format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)" i trädet.
36. Välj "format\Root: Sequence(Root)\Rows: Sequence 1..* (Rows)\Fields: Sequence 1..1 (Fields)\IBAN: String(IBAN)" i trädet.
37. Klicka på Lägg till datakälla.
38. I formelfältet anger du "check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)".
    * check_codes.verifyMOD1271_36(format.Root.Rows.Fields.IBAN)  
39. Klicka på Spara.
40. Stäng sidan.
    * Valideringsvillkoren har konfigurerats för att returnera FALSE för någon ogiltig IBAN-kod genom att kalla den befintliga metoden "verifyMOD1271_36" av programklassen "ISO7064". Observera att värdet i IBAN-koden definieras dynamiskt vid körning som argument för att anropa metoden baserat på innehållet i parsning TXT-fil.   
41. Klicka på Redigera meddelande.
42. I formelfältet anger du "'CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)".
    * CONCATENATE("Invalid IBAN code has been found:  ", format.Root.Rows.Fields.IBAN)  
43. Klicka på Spara.
44. Stäng sidan.
45. Klicka på Spara.
46. Stäng sidan.

## <a name="run-the-format-mapping"></a>Kör mappning av filformat
För testningsändamål, utför formatmappning med den SampleIncomingMessage.txt-fil som du tidigare hämtade. Skapade utdata kommer att inkludera data som importeras från den valda TXT-filen och fyller i den anpassade datamodellen när den verkliga importen sker.   
1. Klicka på Kör.
    * Klicka på Bläddra och navigera till filen SampleIncomingMessage.txt som du hämtade tidigare.  
2. Klicka på OK.
    * Granska utdata i XML-format, vilket representerar de data som har importerats från den valda filen och integrerats i datamodellen. Observera att endast 3 raderna i importerade TXT-filen har bearbetats. IBAN-kod på rad 4 som inte gäller hoppades över och ett felmeddelande ges i informationsloggen.  

