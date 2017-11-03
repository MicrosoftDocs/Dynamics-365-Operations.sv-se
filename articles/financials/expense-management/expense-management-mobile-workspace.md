---
title: "Mobil arbetsyta för utgiftshantering"
description: "Det här avsnittet innehåller information om mobil arbetsyta för Utläggshantering. Den här arbetsytan låter användarna hämta och skicka ett kvitto så att de kan bifogas till en utgiftsrapport senare. Användare kan snabbt skapa en utgiftsrad med en kopplad inleverans och skapa och hantera sina utgiftsrapporter."
author: KimANelson
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 7ce4c9d13a8686c82af8acad39d68858e52ba520
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="expense-management-mobile-workspace"></a>Mobil arbetsyta för utläggshantering

[!include[banner](../includes/banner.md)]

Det här avsnittet innehåller information om mobil arbetsyta för **Utläggshantering**. Den här arbetsytan låter användarna hämta och skicka ett kvitto så att de kan bifogas till en utgiftsrapport senare. Användare kan snabbt skapa en utgiftsrad med en kopplad inleverans och skapa och hantera sina utgiftsrapporter. Godkännare kan dessutom använda den mobila arbetsytan **utgiftshantering** för att visa kostnadsrapporter som har tilldelats till dem och antingen godkänna eller avvisa de utgiftsrapporterna.


Denna mobila arbetsyta är avsedd att användas med mobilappen Microsoft Dynamics 365 for Unified Operations.


## <a name="overview"></a>Översikt

Många organisationer kräver att en kopia av ett kvitto ska kopplas till en reserelaterad eller affärsrelaterad utgiftsrapport som medarbetaren skickar till dig. Den mobila arbetsytan **utgiftshantering** låter användare snabbt skapa nya utgiftsrader med ett bifogad foto på ett kvitto på den mobila enheten efter eget val. Användare kan även fånga en bild av en inleverans och sedan koppla den till en utgiftsrapport. Medarbetare kan också skapa och hantera sina utgiftsrapporter och skicka dem för godkännande och ersättning genom att använda sin mobilenhet.


Särskilt den mobila arbetsytan **Utgiftshantering** låter användarna utföra följande uppgifter:

- Ta en bild av en inleverans och överföra den till Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. En användare kan sedan bifoga den bilden i en utgiftsrapport senare.
- Överför en fil som ett insamlat kvitto. En användare kan sedan bifoga den filen i en utgiftsrapport senare.
- Skapa en ny utgiftsrad med en kopplad inleverans. En användare kan sedan lägga till artikeln i en utgiftsrapport senare och skicka det för godkännande och återbetalning.

Om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli-uppdateringen 2017), kan du även använda dessa funktioner:

- Skapa en ny utgiftsrapport.
- Koppla kreditkortstransaktioner och andra tidigare skapade utgifter i en utgiftsrapport.
- Skapa en ny utgift för en utgiftsrapport.
- Koppla ett kvitto till några utgifter för en utgiftsrapport, antingen med ett foto på kvittot eller genom att överföra en fil som insamlat kvitto.
- Beroende på företagets utgiftspolicy, lägg till gäster för en utgift.
- Beroende på företagets utgiftspolicy, specificera utgifter.
- Skicka en utgiftsrapport för godkännande och återbetalning.
- Godkänn eller avvisa utgiftsrapporter som du tilldelat en godkänner till.

## <a name="prerequisites"></a>Förutsättningar
Kraven varierar baserat på versionen av Microsoft Dynamics 365 som har distribuerats i organisationen.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Förutsättningar om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli-uppdateringen 2017) 
Om Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli-uppdateringen 2017) används inom din organisation, måste systemadministratören publicera den mobila arbetsytan **Utgiftshantering**. Instruktioner finns i [Publicera en mobil arbetsyta](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Krav om du använder Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare
Om Microsoft Dynamics 365 for Operations version 1611 med plattformsuppdatering 3 eller senare har använts i organisationen måste systemadministratören uppfylla följande krav. 

<table>
<thead>
<tr class="header">
<th>Förutsättning</th>
<th>Roll</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implementera KB 4019015.</td>
<td>Systemadministratör</td>
<td>KB 4019015 är X ++ uppdatering eller snabbkorrigering av metadata som innehåller den mobila arbetsytan för <strong>Utgiftshantering</strong>. Om du vill implementera KB 4019015 måste systemadministratören göra följande.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Hämta snabbkorrigering av metadata från Microsoft Dynamics AX Lifecycle Services(LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Snabbkorrigering av metadata</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Skapa ett driftfärdigt paket</a> som innehåller modellerna <strong>ApplicationSuite</strong> och modellen <strong>ExpenseMobile</strong> och överför sedan det driftfärdiga paketet till LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Tillämpa ett distribuerbart paket</a></li>
</ol></td>
</tr>
<tr class="even">
<td>Publicera mobila arbetsytan <strong>Utgiftshantering</strong>.</td>
<td>Systemadministratör</td>
<td>Se <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicera en mobil arbetsyta</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Hämta och installera mobilappen Dynamics 365 for Operation.
Hämta och installera mobilappen Dynamics 365 for Unified Operations:

- [För Android-telefoner](https://go.microsoft.com/fwlink/?linkid=850662)
- [För iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logga in på mobilappen
1. Starta appen i din mobila enhet.
2. Ange din webbadress för Dynamics 365.
4. Första gången du loggar in uppmanas du ange användarnamn och lösenord. Ange dina autentiseringsuppgifter.
5. När du loggar in visas tillgängliga arbetsytor för ditt företag. Observera att om systemadministratören publicerar en ny arbetsyta senare kan du dra om du vill uppdatera listan över mobila arbetsytor.


[![Dra för att uppdatera](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Skapa en inleverans med hjälp av mobil arbetsyta för utgiftshantering

1. På din mobila enhet öppnar du arbetsytan **Utgiftshantering**.
2. Välj **Samla in kvitto**.
3. Välj **ta foto** eller **Välj bild**.
4. Gör något av följande:

    - Om du har valt **ta foto**, gör du följande:

        1. Du förflyttas till kameran på din mobila enhet så att du kan ta ett foto på kvittot. När du är klar med en bild klickar du på **OK** för att acceptera fotot.
        2. Valfritt: Ange ett namn för bilden och ange eventuella noteringar.

    - Eller om du har valt **Välj bild**, gör du följande:

        1. Välj en bild i listan.
        2. Valfritt: Ange ett namn för bilden och ange eventuella noteringar.

5. Välj **Klar**.

## <a name="quickly-enter-expenses-by-using-the-expense-management-mobile-workspace"></a>Snabb utgiftspost med mobil arbetsyta för utgiftshantering
1. På din mobila enhet öppnar du arbetsytan **Utgiftshantering**.
2. Välj **snabb utgiftspost**.
3. Välj kategori för utgiften. Du kan se en lista över de utgiftskategorier som laddas i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information för utvecklare finns under [mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Om kategorin inte finns i listan, välj **Sök** för att göra en onlinesökning. Sök efter kostnadskategori eller växla om du vill söka efter utgiftstyp.
4. Ange transaktionsdatum för utgiften.
5. Valfritt: Ange handlare för utgiften.
6. Ange belopp för utgiften.
7. Välj valutakod för utgiften. Du kan se en lista över de valutakoder som laddas i ditt program för användning offline. Upp till 400 valutor laddas som standard, men en utvecklare kan ändra detta antal. Mer information för utvecklare finns under [mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Om valutan inte finns i listan, välj **Sök** för att göra en onlinesökning. Sök efter valuta eller växla om du vill söka efter namnet.
8. Välj **ta foto** eller **Välj bild**.
9. Gör något av följande:

    - Om du valde **Ta foto** förflyttas du till kameran på din mobila enhet så att du kan ta ett foto på kvittot. När du är klar med en bild klickar du på **OK** för att acceptera fotot.
    - eller om du har valt **Välj bild**, markerar du en bild i listan.

10. Välj **Klar**.

## <a name="approve-an-expense-report-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Godkänn en utgiftsrapport med hjälp av mobilaarbetsytan utgiftshantering (om du använder uppdateringen juli 2017)
1. På din mobila enhet öppnar du arbetsytan **Utgiftshantering**.
2. **Godkännanden av utgifter** visar antalet utgiftsrapporter som har tilldelats dig för godkännande. Antalet uppdateras ungefär var 30:e minut. Välj **Utgiftsgodkännanden**.

    Listan över utgiftsrapporter som har tilldelats dig för godkännande visas.
    
3. Välj en utgiftsrapport att visa utgiftsinformationen för.
4. Välj en utgift att visa informationen för. Den information som visas för en utgift inkluderar alla inleveranser, gäster och specifikationsdetaljer.
5. Tillbaka på sidan **Reseräkning** väljer du att godkänna eller avvisa utgiftsrapporten.
6. Ange eventuella kommentarer för godkännande av åtgärden.
7. Välj **Klar**.

## <a name="create-a-new-expense-report-and-submit-it-for-approval-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Skapa en ny utgiftsrapport och skicka den för godkännande med hjälp av mobila arbetsytan utgiftshantering (om du använder uppdateringen juli 2017)
1. På din mobila enhet öppnar du arbetsytan **Utgiftshantering**.
2. Välj **Utgiftspost**.
3. Välj **ny rapport**, eller markera en befintlig utgiftsrapport i listan.
4. För nya utgiftsrapporter anger du syftet och eventuell ytterligare information som är tillgänglig. Informationen beror på sättet som utgiftshantering har konfigurerats för företaget.
5. Välj **Klar**.
6. Lägg till befintlig utgifter, till exempel kreditkortstransaktioner till utgiftsrapporten och markera **bifoga**.
7. Välj en eller flera utgifter i listan.
8. Välj **Klar**.
9. För att lägga till en ny utgift i utgiftsrapporten, välj **ny utgift**.
10. Välj kategori för utgiften. Du kan se en lista över de utgiftskategorier som laddas i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information för utvecklare finns under [mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Om kategorin inte finns i listan, välj **Sök** för att göra en onlinesökning. Sök efter kostnadskategori eller växla om du vill söka efter utgiftstyp.
11. Valfritt: Ange handlare för utgiften.
12. Ange transaktionsdatum för utgiften.
13. Ange belopp för utgiften.
14. Välj valutakod för utgiften. Du kan se en lista över de valutakoder som laddas i ditt program för användning offline. Upp till 400 valutor laddas som standard, men en utvecklare kan ändra detta antal. Mer information för utvecklare finns under [mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Om valutan inte finns i listan, välj **Sök** för att göra en onlinesökning. Sök efter valuta eller växla om du vill söka efter namnet.
15. Välj **Klar**.
16. Lägg till fler detaljer till utgiften genom att markera **lägg till fler detaljer**. Fälten som är tillgängliga beror på konfigurationen av utgiftshantering för ditt företag.
17. Om företagets policy kräver inleverans för utgiften markerar du **inleveranser**, och gör sedan följande:

    1. Välj **Hämta inleverans** eller **koppla inleverans**.
    2. Gör något av följande:

        - Eller om du har valt **Samla in inleverans**, gör du följande:

            1. Välj **ta foto** eller **Välj bild**.
            2. Gör något av följande:

                - Om du har valt **ta foto**, gör du följande:

                    1. Du förflyttas till kameran på din mobila enhet så att du kan ta ett foto på kvittot. När du är klar med en bild klickar du på **OK** för att acceptera fotot.
                    2. Valfritt: Ange ett namn för bilden och ange eventuella noteringar.

                - Eller om du har valt **Välj bild**, gör du följande:

                    1. Välj en bild i listan.
                    2. Valfritt: Ange ett namn för bilden och ange eventuella noteringar.

            3.  Välj **Klar**.

        - Eller om du har valt **Bifoga inleverans**, gör du följande:

            1.  Välj en eller flera bilder i listan.
            2.  Välj **Klar**.

    3. För att återgå till utgiftsdetaljerna, klicka på knappen **Bakåt** .

18. Om företagets policy kräver gäster för utgiften markerar du **gäster**, och gör sedan följande:

    1. Välj **gäst**, **tidigare gäster**, eller **medarbetare**.
    2. Gör något av följande:

        - Om du har valt **gäst**, gör du följande:

            1. Ange namnet på gästen
            2. Valfritt: Ange organisation och/eller land för gästen.
            3. Valfritt: Ange gästens titel.
            4. Välj **Klar**.

        - Eller om du har valt **Tidigare gäst**, gör du följande:

            1. Välj en eller flera tidigare gäster i listan. Du kan visa en lista med tidigare gäster som du har lagt till tidigare kostnadsrapporter som läses in i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information för utvecklare finns under [mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Om dina tidigare gäster inte finns i listan, välj **Sök** för att göra en onlinesökning. Sök efter namn eller gå till sök efter organisation, land eller titel.
            2. Välj **Klar**.

        - Om du har valt **Medarbetare**, gör du följande:

            1. Välj en eller flera medarbetare i listan. Du kan se en lista över medarbetare som laddas i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information för utvecklare finns under [mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Om medarbetare inte finns i listan, välj **Sök** för att göra en onlinesökning. Sök efter namn eller gå till sök efter företag eller titel.
            2. Välj **Klar**.

    3. För att återgå till utgiftsdetaljerna, klicka på knappen **Bakåt** .

19. Om företagets policy kräver att utgiften specificeras markerar du **specificera**, och gör sedan följande:

    1. Välj startdatum att specificera.
    2. Välj **Lägg till specifikation**.
    3. Välj underkategori för utgiftsspecifikation. Du kan se en lista över de underskategorier som laddas i ditt program för användning offline. 50 objekt laddas som standard, men en utvecklare kan ändra detta antal. Mer information för utvecklare finns under [mobil plattform](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Om underkategorin inte finns i listan, välj **Sök** för att göra en onlinesökning. Sök efter underkategori för utgift.
    4. Ange ett transaktionsbelopp för specifikationen.
    5. Redigera transaktionsdatum om det är obligatoriskt.
    6. Välj **Klar**.
    7. Upprepa föregående steg tills du har lagt till alla specifikationer för det valda datumet.
    8. För extra dagar kan du välja **kopiera till nästa dag** om du vill kopiera specifikationer till nästa dag. Alternativt kan du välja datum att specificera och lägga till specifikationer som du gjorde för det första datumet.
    9. När du är klar med att specifiera utgifterna väljer du knappen **tillbaka** för att gå tillbaka till utgiftsinformationen.

20. Klicka på knappen **Tillbaka** för att gå tillbaka till sidan **Utgiftsrapport**.
21. Upprepa föregående steg tills du har lagt till alla utgifter.
22. Välj **skicka**.
23. Ange eventuella kommentarer för godkännaren.
24. Välj **Klar**.

