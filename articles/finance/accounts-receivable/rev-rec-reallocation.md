---
title: Omallokering vid intäktsredovisning
description: Det här avsnittet innehåller information om omallokering, vilket gör det möjligt för organisationer att beräkna om intäktspriser när villkoren för en avyttring ändras. Det innehåller länkar till andra avsnitt som beskriver hur du redovisar intäkter i flera olika scenarier.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2d961cb4eedda6265b4acd8dbd6f82e8026373fa
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820579"
---
# <a name="revenue-recognition-reallocation"></a>Omallokering vid intäktsredovisning

[!include [banner](../includes/banner.md)]

Med omallokering kan organisationer beräkna om intäktspriser när villkoren för en avyttring ändras. Vid intäktsredovisning betraktas försäljningsorderdokumenten utgöra kontraktet.

Din organisation måste själv ta reda på omallokering behövs. Att lägga till en ny rad på en försäljningsorder, eller att lägga till en ny försäljningsorder för en kund, kanske inte innebär en ändring av kontraktet. Följande scenarier kan kräva omallokering:

- En kund har lagt till artiklar på en försäljningsorder, eller tagit bort artiklar från försäljningsordern, efter att ordern helt eller delvis fakturerats.
- Flera försäljningsorder, antingen i bekräftat eller fakturerat tillstånd, har registrerats för samma förhandlade kontrakt.
- En kund har returnerat eller fått en kredit för en artikel efter att den ursprungliga försäljningsordern var helt eller delvis fakturerad.

Det finns några viktiga begränsningar för omallokeringsprocessen:

- Processen kan bara köras en gång. Därför är det viktigt att du bara kör den när alla ändringar har slutförts.
- Processen kan inte köras på projektförsäljningsorder.
- Om flera försäljningsorder är inblandade måste de gälla för samma kundkonto.
- Alla försäljningsorder som omallokeras måste vara i samma transaktionsvaluta.
- Processen kan inte återställas eller ångras när den har körts.

## <a name="set-up-reallocation"></a>Konfigurera omallokering

En parameter påverkar omallokeringsprocessen.

Eftersom omallokering kan göras på en försäljningsorder som är delvis eller helt fakturerad, måste eventuella tidigare redovisningsposter för fakturan korrigeras med de nya, omallokerade intäktspriserna. Korrigeringen görs genom att den ursprungliga fakturans redovisningspost återförs och en ny redovisningspost bokförs som baseras på de omallokerade intäktspriserna.

Varje organisation måste bestämma om korrigeringen enbart ska uppdatera redovisningen eller om den även ska uppdatera kundreskontra. Det beslut som fattas avgör vilken lämplig inställning som ska anges i alternativet **Bokför fakturakorrigeringar i Kundreskontra** på fliken **Intäktsredovisning** på sidan **Redovisningsparametrar** (**Intäktsredovisning \> Inställningar \> Redovisningsparametrar**). Vilken inställning som ska väljas beror på scenariot. Mer information om möjliga scenarier finns i länkarna i avsnittet [Scenarier för omallokering](#scenarios-for-reallocation)senare i det här avsnittet.

[![Fliken Intäktsredovisning på sidan Redovisningsparametrar](./media/01_RevRecScenarios.png)](./media/01_RevRecScenarios.png)

Om alternativet **Bokför fakturakorrigeringar i Kundreskontra** är inställt på **Ja** leder omallokeringsprocessen till följande resultat:

- Ett kreditdokument skapas i kundreskontra för att återföra fakturan som måste korrigeras.

    - Kreditdokumentet återanvänder det ursprungliga fakturanumret, men "-1" läggs till.
    - Kreditdokumentet kvittas automatiskt mot den ursprungliga fakturan. Om den ursprungliga fakturan redan har kvittats mot ett annat kreditdokument eller en annan betalning återförs kvittningen automatiskt.
    - Kreditdokumentet bokförs i redovisningen för att återföra redovisningsposten som bokfördes på den ursprungliga fakturan. Transaktionsposterna för lager och kostnader för sålda varor (KSV) återförs emellertid inte.

- En ny faktura som baseras på de nya, omallokerade prisbeloppen skapas i kundreskontra.

    - En ny faktura återanvänder det ursprungliga fakturanumret, men "-2" läggs till.
    - Den nya fakturan kvittas automatiskt mot eventuella kreditdokument eller betalningar som tidigare kvittats mot den ursprungliga fakturan.
    - Den nya fakturan bokförs i redovisningen med hjälp av de nya, omallokerade intäktsprisbeloppen. Den bokförs inte på kontona för lager och KSV igen, eftersom dessa poster underhålls i den ursprungliga fakturans redovisningspost.

Om alternativet **Bokför fakturakorrigeringar i Kundreskontra** är inställt på **Nej** leder omallokeringsprocessen till följande resultat:

- En återföringsredovisningspost bokförs bara i redovisningen. All redovisning från den ursprungliga fakturan återförs, utom kontoposterna för lager och KSV.
- En ny redovisningspost bokförs bara i redovisningen baserat på de nya, omallokerade intäktspriserna. Den bokförs inte på kontona för lager och KSV igen, eftersom dessa poster underhålls i den ursprungliga fakturans redovisningspost.
- Fakturan på sidan **Kundtransaktioner** varken påverkas eller ändras, men återspeglar fortfarande den ursprungliga redovisningsposten. Det finns ingen referens till återföringen eller nya redovisningsposter.

Så som tidigare rapporterats kan du uppdatera enbart redovisningen, eller så kan du uppdatera både redovisningen och kundreskontra. Båda tillvägagångssätten har fördelar och nackdelar. Vi rekommenderar att du undersöker vilka behov din organisation har för att avgöra vilket alternativ du ska använda. Om du uppdaterar både redovisningen och kundreskontra visas de korrekta redovisningsposterna på den nya fakturan och de kan visas från dokumentet på sidan **Kundtransaktioner**. Dessutom använder kvittningsprocessen de uppdaterade redovisningsposterna för att bokföra kassarabatter och vinster eller förluster. Å andra sidan visas kreditdokumentet och den nya fakturan på kundutdrag och åldersfördelningsrapporter, på samma sätt som andra kreditdokument och kundfakturor. Beskrivningen av dessa dokument visar att de har skapats genom en korrigering av redovisningen.

## <a name="run-the-reallocation-process"></a>Köra omallokeringsprocessen

Du startar omallokeringsprocessen genom att välja **Allokera om pris med nya orderrader** på en försäljningsorder du behöver omallokera. Du kan också gå till **Intäktsredovisning \> Periodiska uppgifter \> Allokera om pris med nya orderrader** och sedan ange lämpliga filter, till exempel kundkontot.

[![Sidan Allokera om pris med nya orderrader](./media/02_RevRecScenarios.png)](./media/02_RevRecScenarios.png)

Det övre rutnätet på sidan **Allokera om pris med nya orderrader** har namnet **Försäljning**. Här visas försäljningsorder för kunden. Välj de försäljningsorder som ska allokeras om. Du kan inte välja projektförsäljningsorder eftersom projektförsäljningsorder inte kan allokeras om. Du kan heller inte välja försäljningsorder som redan har ett omallokerings-ID, eftersom andra typer av försäljningsorder än projektförsäljningsorder bara kan allokeras om en gång. Om en försäljningsorder har ett omallokerings-ID har den redan markerats för omallokering av en annan användare.

Det nedre rutnätet på sidan har namnet **Rader**. När du har valt en eller flera försäljningsorder i rutnätet **Försäljning** visar rutnätet **Rader** försäljningsorderraderna. Välj de försäljningsorderrader som ska allokeras om. Om du bara har valt en försäljningsorder måste raderna i samma försäljningsorder allokeras om. Denna situation kan uppstå när en av försäljningsorderraderna har fakturerats tidigare, och sedan har en ny rad lagts till, eller när en befintlig rad har tagits bort eller annullerats. Om en rad har tagits bort visas den inte i rutnätet. Därför kan den inte väljas. Den beaktas dock fortfarande när omallokeringsprocessen körs.

När du har valt försäljningsorderraderna använder du knapparna i åtgärdsfönstret enligt beskrivningen här:

- **Uppdatera omallokering** – Beräkna de nya intäktsprisbeloppen för de valda försäljningsorderraderna. Om en rad har tagits bort eller annullerats görs omallokeringen bara för de befintliga rader som du har valt. Följande bild visar ett exempel på försäljningsorderrader innan omallokeringen uppdateras.

    [![Försäljningsorderrader innan omallokeringen uppdateras](./media/03_RevRecScenarios.png)](./media/03_RevRecScenarios.png)

    De nya intäktsprisbeloppen visas i kolumnen **Omallokerat belopp** i rutnätet **Rader**. Vid den här punkten har omallokeringen bearbetats, men den har ännu inte beräknats. Följande bild visar ett exempel på försäljningsorderrader efter att omallokeringen uppdateras.

    [![Försäljningsorderrader efter att omallokeringen uppdaterats](./media/04_RevRecScenarios.png)](./media/04_RevRecScenarios.png)

- **Bearbeta** – Bearbeta eller bokför de omallokerade intäktspriserna. När du har valt den här knappen går det inte att återföra omallokeringen. Om du inte valde **Uppdatera omallokering** innan du valde **Bearbeta** körs omallokeringen automatiskt.

    - Om ingen försäljningsorderrad har fakturerats, uppdateras intäktsprisbeloppen på alla försäljningsorder som valts för omallokering.
    - Om en eller flera försäljningsorderrader har fakturerats bokförs korrigerande redovisningsposter, och alla intäktsplansdetaljer som har skapats för den fakturerade försäljningsorderraden korrigeras.

- **Förväntad verifikation** – Visa en förhandsgranskning av redovisningsposterna som har skapats för alla försäljningsorderrader som har fakturerats. Om inga rader har fakturerats visas ingenting. Om du inte valde **Uppdatera omallokering** innan du valde **Förväntad verifikation** körs omallokeringen automatiskt.
- **Intäktsfördelning** – Öppna en sida som visar allokeringen av intäktspriset för alla valda rader. Du kan inte ändra någon information på sidan. Här visas de radbelopp som användes för att göra omallokeringen.

    [![Radbelopp som har använts för omallokering](./media/05_RevRecScenarios.png)](./media/05_RevRecScenarios.png)

- **Återställ data för den valda kunden** – Om omallokeringsprocessen startats men inte slutförts kan du bara rensa data i omallokeringstabellen för den valda kunden. Du markerar till exempel flera försäljningsorderrader för omallokering, lämnar sidan öppen utan att välja **Bearbeta** och sedan uppnås sidans tidsgräns. I så fall förblir försäljningsorderraderna markerade och kan inte användas av en annan användare för att slutföra omallokeringsprocessen. Sidan kan till och med vara tom när den öppnas. I den här situationen kan knappen **Återställ data för den valda kunden** användas för att rensa obearbetade försäljningsorder så att en annan användare kan slutföra omallokeringsprocessen.

## <a name="scenarios-for-reallocation"></a>Scenarier för omallokering

I följande avsnitt beskrivs olika scenarier för intäktsredovisning:

- [Omallokering vid intäktsredovisning – Scenario 1](rev-rec-reallocation-scenario-1.md) – Två försäljningsorder registreras, men de bekräftas bara. Samma scenario kommer att ge liknande resultat om fler än två försäljningsorder är i ett bekräftat tillstånd.
- [Omallokering vid intäktsredovisning – Scenario 2](rev-rec-reallocation-scenario-2.md) – Två försäljningsorder registreras, och sedan lägger kunden till en artikel i kontraktet efter att den första försäljningsordern har fakturerats.
- [Omallokering vid intäktsredovisning – Scenario 3](rev-rec-reallocation-scenario-3.md) – En ny rad läggs till i en befintlig, fakturerad försäljningsorder.
- [Omallokering vid intäktsredovisning – Scenario 4](rev-rec-reallocation-scenario-4.md) – En rad tas bort från en befintlig, delvis fakturerad försäljningsorder.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]