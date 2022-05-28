---
title: Listsida för kundtransaktioner
description: Det här avsnittet innehåller information om Listsida för kundtransaktioner för Microsoft Dynamics 365 Finance.
author: abruer
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: ca6c9a054b47a5cdb6b001b7621f65797553fa21
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734787"
---
# <a name="customer-transactions-list-page"></a>Listsida för kundtransaktioner

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Visa kvittningar

Knappen **Visa kvittningar** i åtgärdsfönstret ger snabb tillgång till kvittningshistoriken och mer information om kvittningstransaktionen. Du kan också visa ytterligare transaktioner som är relaterade till den valda transaktionen, antingen eftersom de tillhörde samma kvittning eller eftersom de är betalningar som skapades i samma betalningsjournal.

1. Välj **Kundreskontra \> Alla kunder**.
2. Markera en kund med transaktioner och sedan i åtgärdsfönstret, på fliken **kund**, välj **transaktioner**.
3. Markera en transaktion att undersöka och markera **Visa kvittningar** i åtgärdsfönstret.

    Dialogrutan **Visa kvittningar** visas och visar den valda transaktionen och alla dokument som har kvittats mot den. Denna dialogruta liknar kvittningshistorikvyn, men den innehåller alla relaterade dokument.

4. I dialogrutan kan du utföra olika uppgifter. Markera en eller flera verifikationer och välj en av följande knappar:

    - **Visa relaterade** – visa alla transaktioner i betalningsjournalen och allmänna journaltransaktioner för den kund som har skapats i journalerna där dokumenten som visas i listan skapades. Till exempel om en betalning visas kommer alla betalningar i betalningsjournalen där den skapades att visas. Om en faktura eller betalning visas och den skapades i en redovisningsjournal visas alla dokument i den redovisningsjournalen som den skapades i. Alla kvittningar som är relaterade till listan med dokument visas också. Medan du visar relaterade betalningar ändras etiketten på den här knappen till **Visa kvittningar**. Välj **Visa kvittningar** om du endast vill visa transaktioner som visades när du öppnade dialogrutan **Visa kvittningar**.
    - **Visa historik** – Visa kvittningshistoriken för verifikationerna. Välj **Stäng** för att stänga dialogrutan.
    - **Visa redovisning** – Visa alla verifikationer som är relaterade till de valda dokumenten. Välj **Stäng** för att stänga dialogrutan.
    - **Exportera** – Exportera de valda verifikationerna till Microsoft Excel.
    - **Kvitta transaktioner** – Denna knapp visas endast om det ursprungliga dokumentet som valdes inte kvittats helt. När du väljer den här knappen **kvitta transaktioner** där du kan välja transaktioner för kvittning.
    - **Ångra kvittningar** – Denna knapp visas endast om det ursprungliga dokumentet som valdes inte kvittats helt. När du väljer denna knapp visas dialogrutan **Ångra kvittningar** där du kan ångra kvittningar som har gjorts för det dokumentet.

## <a name="global-transactions"></a>Globala transaktioner

Knappen **globala transaktioner** visas även på listsidan **kundtransaktioner**. Den här knappen låter dig visa alla transaktioner för en kund i alla juridiska personer. Listsidan **Kundtransaktioner** visar endast transaktioner för de juridiska personer som användaren har tillgång till, baserat på användarens säkerhetsinställningar.

Listsidan visar alla transaktioner för kunder som har samma part-ID som kunder du startade med. Om t.ex. kunder US-001 i en juridisk person har samma part-ID som kunder DE-001 i en annan juridisk person, visas alla transaktioner för både kunder-ID:n.

Menyerna på listsidan **kundertransaktioner** varierar beroende på den juridiska personen för transaktionen. En funktion är t.ex. bara tillgänglig för Schweiziska rättssubjekt visas menyalternativen för funktionen exempelvis bara när en schweizisk transaktion är markerad.

Följ dessa steg om du vill använda funktionen.

1. Välj **Kundreskontra \> Alla kunder**.
2. Välj en kund och sedan i åtgärdsfönstret på fliken **kund** i gruppen **Transaktioner** väljer du **Globala transaktioner**.

## <a name="more-transaction-filters"></a>Fler transaktionsfilter 

Filtret för att visa öppna transaktioner har ersatts av ett nytt filter där du kan visa flera kombinationer av transaktioner. Följande alternativ finns tillgängliga **Visa**:

- **Alla** – Visa alla transaktionerna för de valda kunderna (öppna och stängda).
- **Stängda** – Visa endast transaktioner som har kvittats och stängts helt.
- **Öppen** – Visa endast transaktioner som inte har kvittats.
- **Öppna inklusive stängda på eller efter datumet** – Visa endast transaktioner som inte har kvittats helt eller efter ett datum som du anger. När du väljer det här alternativet kan du ändra datumet som visas bredvid filtret. Transaktioner som har värdet **Senaste kvittningsdatumet** på eller efter det datum som du anger visas i listan, även om dessa transaktioner kvittas fullständigt per aktuellt datum. Saldot representerar emellertid saldon per aktuellt datum, inte på det valda datumet.

Markera kryssrutan **Dölj valutaomvärderingar** för att dölja transaktioner för valutaregistrering.

## <a name="modify-due-dates-and-discount-dates"></a>Ändra förfallodatum och rabattdatum

Du kan uppdatera förfallodatum och rabattdatum för öppna kundtransaktioner. I version 8.1 kan du nu lägga till förfallodatum till listsidan **kundtransaktioner**. Genom att klicka på förfallodatumet på listsidan **kundtransaktioner** kan du även ändra förfallodatum, rabattdatum, betalningsvillkor och kassarabattsvillkoren i dialogrutan **Uppdatera förfallodatum och kassarabattdatum**.

### <a name="activate-the-feature"></a>Aktivera funktionen

Lägga till förfallodatum till listsidan **kundtransaktioner** och ändra inställningar för betalning för en transaktion med dialogrutan **Uppdatera förfallodatum och kassarabattdatum**, följ anvisningarna.

1. Välj **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
2. På fliken **kvittningar**, ange alternativet **Visa förfallodatum och tillåt redigering** till **Ja**.
3. Om du vill aktivera funktionen har nya fält lagts till kundtransaktioner. Fälten fylls när en ny transaktion slutförs. De kan även fyllas i när du öppnar dialogrutan **Uppdatera förfallodatum och kassarabattdatum**. När du anger alternativet **Visa förfallodatum och tillåt redigering** till **Ja**, visas dialogrutan **uppdatera betalningsinformation**.  För att uppdatera befintliga transaktioner omedelbart, välj **uppdatera alla befintliga transaktioner**. Alternativt kan du också fylla i fälten för nya transaktioner genom att välja **Fortsätt utan uppdatering**.

Förfallodatumet läggs nu till på listsidan **kundtransaktioner** och blir det lättare ändra förfallodatum och kassarabattdatum för transaktioner.

### <a name="modify-the-payment-settings"></a>Ändra inställningar för betalning

Listsidan **kundtransaktioner** visar alla transaktioner för en kund. När du väljer ett förfallodatum för en transaktion visas dialogrutan **Uppdatera förfallodatum och kassarabattdatum**. Den här dialogrutan visar basdatum för förfallodatum och beräkning av rabatter, förfallodatum, betalningsvillkor, kassarabattsvillkor och datum för kassarabatten.

Varje fält har en annan effekt på transaktionen vid redigering:

- **Redigera basdatum** – Förfallodagen och rabattdatumet ändras som om basdatumet är dokumentdatumet.
- **Redigera förfallodatum** – Endast förfallodatumet ändras.
- **Redigera rabattdatum** – Endast rabattdatum ändras.
- **Redigera betalningsvillkoren** – Förfallodatumet ändras utifrån basdatum och betalningsvillkoren.
- **Redigera villkoren för kassarabatt** – Kassarabatterna ändras utifrån basdatum och kassarabattsvillkoren.

När du är klar med redigeringen av betalningdinställningar väljer du **Stäng** att spara dina ändringar.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
