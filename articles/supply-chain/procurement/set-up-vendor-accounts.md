---
title: "Skapa leverantörskonton"
description: "I det här avsnittet beskrivs de informationstyper som du måste ange när du skapar ett nytt leverantörskonto."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: smmContactPerson, VendBankAccounts, VendTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 191053
ms.assetid: 06168199-7c54-40e9-a038-4eb274ca958d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4a20fca7420e7bd546e29278b40046d69a81aac6
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-vendor-accounts"></a>Skapa leverantörskonton

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs de informationstyper som du måste ange när du skapar ett nytt leverantörskonto.

När du skapar ett leverantörskonto anger du information om leverantören. Den här informationen används för att automatiskt ange data i dokument och för att spåra aktivitet som rör leverantören. Du kan till exempel konfigurera följande information för en leverantör:

-   Tilldela en leverantörsgrupp. Varje leverantör måste tilldelas en leverantörsgrupp. Leverantörerna i en leverantörsgrupp har parametrar som de delar. De kan till exempel ha samma betalningsvillkor.
-   Konfigurera leverantören för katalogimport Leverantörer kan skapa en fil som innehåller katalogen med deras artiklar och tjänster. Denna fil kan överföras så att dina medarbetare kan beställa från leverantören.
-   Tilldela anskaffningkategorier till leverantören.
-   Tillåt en befintlig leverantör att göra affärer med en annan juridisk person i din organisation.
-   Spärra en leverantör för specifika typer av transaktioner.
-   Ställ in bankinformation för leverantören, så att du kan skicka betalningar elektroniskt.
-   Ställ in moms, leverans-, faktura - och betalningsinformation för leverantören. Som standard dessa inställningar kopieras till nya dokument som du skapar för leverantören.
-   Ställ in standardekonomiska dimensioner som används för att automatiskt bokföra transaktioner med leverantör till affärsredovisningskonton.

För att påskynda processen med att skapa leverantörskonton kan du skapa mallar. Om du vill skapa en mall klickar du på sidan **Leverantör** och på åtgärdsfönstret klickar du på **Alternativ** &gt; **Registrera uppgifter**. Klicka sedan på **Kontomall för företag**. Kontomallar för företag delas med andra användare.  

Du kan också skapa en användarmall för ditt eget bruk. Du kan inte ta bort en leverantör som är associerad med andra poster, till exempel kontakter eller produkter.

## <a name="vendor-account-numbers"></a>Leverantörens kontonummer
Kontonumret är ett unikt ID för en leverantör. Du kan konfigurera kontonummer så att dessa genereras automatiskt när du skapar en leverantör. Du kan även konfigurera nummerserien så att kontonummer anges manuellt. Du kanske till exempel vill använda leverantörens telefonnummer som ID.

## <a name="vendor-organizations-and-individual-vendors"></a>Leverantörorganisationer och enskilda leverantörer
När du skapar ett nytt leverantörskonto måste du välja om leverantören är en person eller en organisation. Ditt val påverkar den information som du måste fylla i för leverantören. För en person inkluderar den här informationen förnamn, efternamn och rubrik. För en organisation inkluderar den här informationen organisationsnummer samt antalet medarbetare.

## <a name="addresses"></a>Adresser
För varje leverantör kan du definiera flera adresser, som var och en används för ett annat syfte. Du kan till exempel skapa en adress som har ett syfte för **Faktura**. Om du istället vill betala en leverantör med check, kan du konfigurera en adress med syftet **Remittera till**. Om du måste ange en adress som ska användas för överföring av pengar till utländska banker ska syftet vara **SWIFT**.

## <a name="vendor-contacts"></a>Leverantörskontakt
Du kan lagra kontakter för en leverantör. Dessa kontakter kan sedan användas för dokument som exempelvis inköpsordrar eller anbudsförfrågan (RFQ).  

Om du vill lägga till leverantörer klickar du på sidan **Alla leverantörer** på fliken **Leverantör** i gruppen **Inställningar** och klickar på **Kontakter** &gt; **Lägg till kontakter**.  

Du kan skapa leverantörskontakter från noll. Alternativt kan du också kopiera information från en annan person som redan är registrerad i Microsoft Dynamics 365 for Finance and Operations och redigera den information som du behöver.  

**Obs!** Att lägga till en kontakt för en leverantör är inte samma sak som att lägga till kontaktinformation för den leverantören. Även om du kan lägga till allmän kontaktinformation för en leverantör kanske du också har flera specifika personer som är kontakter i det företaget, och som alla har sin egen kontaktinformation.  

Du kan inte ta bort en post för kontaktperson om ett dokument refererar till kontakten. I stället kan du avaktivera kontakten.  

Du kan lägga till leverantörskontakter till dina personliga kontakter i Microsoft Office 365. Du måste dock först ställa in synkronisering mellan Finance and Operations och Office 365 i både Microsoft Exchange Server-synkroniseringen och Microsoft Outlook-installationsguiden.

## <a name="vendors-in-different-legal-entities"></a>Leverantörer i olika juridiska personer
Om en leverantör registreras för endast en juridisk person inom din organisation, och andra juridiska personer måste registrera samma leverantör, kan du använda sidan **Lägg till leverantör till en annan juridisk person** för att konfigurera leverantören i syfte att göra affärer med en annan juridisk person. Du måste välja en leverantörsgrupp, en valuta och en undantagsstatus för leverantören i den valda juridiska personen.  

Om flera juridiska personer i din organisation gör affärer med samma leverantör, och varje juridisk person har ett separat leverantörskonto för leverantören, kan du använda den här proceduren för att sammanfoga part-ID:n för leverantörskontona. På så sätt kan information som till exempel adress och antalet medarbetare delas, så att du bara behöver uppdatera den på en enda plats.  

Om du vill slå ihop part-ID:n, följ då dessa steg.

1.  På sidan **Global adressbok**, markera de adressboksposter som representerar leverantören i varje juridisk person som ska inkluderas i mappningen.
2.  I åtgärdsfönstret klickar du **Sammanfoga poster**.

## <a name="agreements"></a>Avtal
När du konfigurerar ett leverantörskonto kanske du också vill registrera de avtal som du har med leverantören. Du kan ställa in pris- och rabattavtal med hjälp av åtgärder för leverantörsposten. Du kan även ställa in ett inköpsavtal på sidan **Inköpsavtal**.

## <a name="putting-a-vendor-on-hold"></a>Spärra en leverantör
Du kan spärra en leverantör för olika transaktionstyper. Följande alternativ är tillgängliga:

-   **Nej** – Inga spärrar har ålagts leverantören.
-   **Faktura** – Inga fakturor kan publiceras för leverantören.
-   **Alla** – Leverantören har spärrats för alla transaktionstyper. Dessa transaktionstyper inkluderar inköpsrekvisitioner, fakturor och betalningar.
-   **Betalning** – Inga betalningar kan skapas för leverantören.
-   **Rekvisition** – Endast inköpsrekvisitioner kan skapas. Inga övriga transaktioner kan skapas.
-   **Aldrig** – Leverantören spärras aldrig för inaktivitet.

När du spärrar en leverantör kan du också ange en orsak och ett datum då spärrstatusen avslutas. Om du inte anger något slutdatum, varar leverantörens spärrade status på obestämd tid.

Du kan massimportera uppdateringar som inte är spärrade till **alla** för leverantörer baserat på de valda kriterierna på sidan **inaktivering av leverantör** och tilldela en orsak till varför leverantören är spärrad.

Följande kriterier används för att inkludera leverantörer som har varit inaktiva under en period, inkludera eller undanta leverantörer som är anställda eller utelämna leverantörer under en respittid före nästa spärr.

- Baserat på hur många dagar som du anger i fältet **i aktivitetsperiod** på sidan **inaktivering av leverantör** beräknar programmet det senaste datumet då leverantören kan ha någon aktivitet som ska anses vara inaktiv. Det vill säga det aktuella datumet minus antalet dagar du anger. Om det finns en eller flera fakturor för leverantören där datumet är senare än det senaste beräknade datumet undantas leverantören från inaktiveringen. Detta kontrolleras även om leverantören har betalningar efter detta datum, öppnar inköpsrekvisitioner, öppnar inköpsorder, begär offerter eller svar.
- Antal dagar i fältet **Respittid före nästa spärr** används för att beräkna det senaste datumet för respittid. Det vill säga det aktuella datumet minus antalet dagar du anger. Detta gäller endast leverantörer som tidigare har inaktiverats. När det gäller en tidigare inaktivering kontrollerar programmet historiken för andra förekomster av inaktivering för leverantören och kontrollerar om senaste inaktiveringen uppstått före det senaste datumet för respittid. Om så är fallet inkluderas leverantören i inaktiveringsprocessen.
- Parametern **inkludera medarbetare** refererar till leverantörer som är kopplade till en medarbetare. Du kan ange om du vill inkludera dessa medarbetare.

Denna process utesluter alltid leverantörer där värdet i fältet **leverantörsspärr** är **aldrig**.

Leverantörer som går igenom valideringen placeras i spärr vilket anger fältvärdet **leverantörsspärr** till **alla** och **orsak** till vad som har valts. En post i spärrningshistoriken skapas för leverantören.

## <a name="vendor-invoice-account"></a>Leverantörsfakturakonto
Du kan ange ett faktureringskonto på leverantörsposten om mer än en leverantör har samma faktureringsadress, eller om en leverantör faktureras via en tredje part. Fakturakontot är det konto till vilket fakturabeloppet krediteras när du skapar en leverantörsfaktura från en inköpsorder. Om du inte anger ett fakturakonto på leverantörsposten används leverantörskontot som fakturakonto.

## <a name="vendor-bank-accounts"></a>Leverantörsbankkonton
Om du måste göra betalningar till ett leverantörsbankkonto kan du ange information om leverantörens bank och bankkonton på sidan **Leverantörsbankkonton**. Du kan också ange information om validering och betalningar för det valda bankkontot. Du kan till exempel lägga till förauktoriseringar till leverantörsbankkonton. Dessa förauktoriseringar kan användas för att verifiera att kontodata är korrekta, till exempel organisationsnummer och kontonummer. Du måste ange ett standardkonto för betalningar till leverantören. När du gör en verklig betalning kan du ändra detta konto till ett av leverantörens andra konton.

## <a name="ledger-accounts"></a>Huvudbokskonton
Du kan ange de standardkonton som automatiskt visas i leverantörsfakturajournalerna för den angivna leverantören. Denna funktion kan vara praktisk om du vanligtvis betalar för samma typer av artiklar eller tjänster från samma leverantörer över tid. När du anger ett standardkonto kan du snabbt och effektivt ange journalposter i fakturajournalen. Standardkontona som du anger används inte för inköpsordrar eller för leverantörsfakturor som anges på sidan **Leverantörsfaktura**.  

Du väljer standardkonton på sidan **Standardkontoinställning**, som du öppnar via fliken **Faktura** på leverantörsposten. De konton som du väljer här visas i den filtrerade listan över konton för leverantörskontot när du anger en journalpost. Du kan ange ett av kontona som ett standardkonto.




