---
title: Listsida för leverantörstransaktioner
description: Det här avsnittet innehåller information om Listsida för leverantörstransaktioner för Microsoft Dynamics 365 Finance.
author: mikefalkner
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 455ff6b2f337af272c63fce08f40de574622ad55c6fb2c3e5b354a9d34843559
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777202"
---
# <a name="vendor-transactions-list-page"></a>Listsida för leverantörstransaktioner

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a>Visa kvittningar

Knappen **Visa kvittningar** i åtgärdsfönstret ger snabb tillgång till kvittningshistoriken och mer information om kvittningstransaktionen. Du kan också visa ytterligare transaktioner som är relaterade till den valda transaktionen, antingen eftersom de tillhörde samma kvittning eller eftersom de är betalningar som skapades i samma betalningsjournal.

1. Välj **Leverantörsreskontra \>Alla leverantörer**.
2. Markera en leverantör med transaktioner och sedan i åtgärdsfönstret, på fliken **leverantör**, välj **transaktioner**.
3. Markera en transaktion att undersöka och markera **Visa kvittningar** i åtgärdsfönstret.

    Dialogrutan **Visa kvittningar** visas och visar den valda transaktionen och alla dokument som har kvittats mot den. Denna dialogruta liknar kvittningshistorikvyn, men den innehåller alla relaterade dokument.

4. I dialogrutan kan du utföra olika uppgifter. Markera en eller flera verifikationer och välj en av följande knappar:

    - **Visa relaterade** – visa alla transaktioner i betalningsjournalen och allmänna journaltransaktioner för den leverantör som har skapats i journalerna där dokumenten som visas i listan skapades. Till exempel om en betalning visas kommer alla betalningar i betalningsjournalen där den skapades att visas. Om en faktura eller betalning visas och den skapades i en redovisningsjournal visas alla dokument i den redovisningsjournalen som den skapades i. Alla kvittningar som är relaterade till listan med dokument visas också. Medan du visar relaterade betalningar ändras etiketten på den här knappen till **Visa kvittningar**. Välj **Visa kvittningar** om du endast vill visa transaktioner som visades när du öppnade dialogrutan **Visa kvittningar**.
    - **Visa historik** – Visa kvittningshistoriken för verifikationerna. Välj **Stäng** för att stänga dialogrutan.
    - **Visa redovisning** – Visa alla verifikationer som är relaterade till de valda dokumenten. Välj **Stäng** för att stänga dialogrutan.
    - **Exportera** – Exportera de valda verifikationerna till Microsoft Excel.
    - **Kvitta transaktioner** – Denna knapp visas endast om det ursprungliga dokumentet som valdes inte kvittats helt. När du väljer den här knappen **kvitta transaktioner** där du kan välja transaktioner för kvittning.
    - **Ångra kvittningar** – Denna knapp visas endast om det ursprungliga dokumentet som valdes inte kvittats helt. När du väljer denna knapp visas dialogrutan **Ångra kvittningar** där du kan ångra kvittningar som har gjorts för det dokumentet.

## <a name="global-transactions"></a>Globala transaktioner

Knappen **globala transaktioner** visas även på listsidan **leverantörstransaktioner**. Den här knappen låter dig visa alla transaktioner för en leverantör i alla juridiska personer. Listsidan **Leverantörstransaktioner** visar endast transaktioner för de juridiska personer som användaren har tillgång till, baserat på användarens säkerhetsinställningar.

Listsidan visar alla transaktioner för leverantörer som har samma part-ID som leverantören du startade med. Om t.ex. leverantör US-001 i en juridisk person har samma part-ID som leverantör DE-001 i en annan juridisk person, visas alla transaktioner för både leverantörs-ID:n.

Menyerna på listsidan **leverantörstransaktioner** varierar beroende på den juridiska personen för transaktionen. En funktion är t.ex. bara tillgänglig för Schweiziska rättssubjekt visas menyalternativen för funktionen exempelvis bara när en schweizisk transaktion är markerad.

Följ dessa steg om du vill använda funktionen.

1. Välj **Leverantörsreskontra** \> **Alla leverantörer**.
2. Välj en leverantör och sedan i åtgärdsfönstret på fliken **Leverantör** i gruppen **Transaktioner** väljer du **Globala transaktioner**.

## <a name="more-transaction-filters"></a>Fler transaktionsfilter

Filtret för att visa öppna transaktioner har ersatts av ett nytt filter där du kan visa flera kombinationer av transaktioner. Följande alternativ finns tillgängliga **Visa**:

- **Alla** – Visa alla transaktionerna för den valda leverantören (öppna och stängda).
- **Stängda** – Visa endast transaktioner som har kvittats och stängts helt.
- **Öppen** – Visa endast transaktioner som inte har kvittats.
- **Öppna inklusive stängda på eller efter datumet** – Visa endast transaktioner som inte har kvittats helt eller efter ett datum som du anger. När du väljer det här alternativet kan du ändra datumet som visas bredvid filtret. Transaktioner som har värdet **Senaste kvittningsdatumet** på eller efter det datum som du anger visas i listan, även om dessa transaktioner kvittas fullständigt per aktuellt datum. Saldot representerar emellertid saldon per aktuellt datum, inte på det valda datumet.

Markera kryssrutan **Dölj valutaomvärderingar** för att dölja transaktioner för valutaregistrering.

## <a name="modify-due-dates-and-discount-dates"></a>Ändra förfallodatum och rabattdatum

Du kan uppdatera förfallodatum och rabattdatum för öppna kundtransaktioner. I version 8.1 kan du nu lägga till förfallodatum till listsidan **leverantörstransaktioner**. Genom att klicka på förfallodatumet på listsidan **leverantörstransaktioner** kan du även ändra förfallodatum, rabattdatum, betalningsvillkor och kassarabattsvillkoren i dialogrutan **Uppdatera förfallodatum och kassarabattdatum**.

### <a name="activate-the-feature"></a>Aktivera funktionen

Lägga till förfallodatum till listsidan **leverantörstransaktioner** och ändra inställningar för betalning för en transaktion med dialogrutan **Uppdatera förfallodatum och kassarabattdatum**, följ anvisningarna.

1. Välj **Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**.
2. På fliken **kvittningar**, ange alternativet **Visa förfallodatum och tillåt redigering** till **Ja**.
3. Om du vill aktivera funktionen har nya fält lagts till leverantörstransaktioner. Fälten fylls när en ny transaktion slutförs. De kan även fyllas i när du öppnar dialogrutan **Uppdatera förfallodatum och kassarabattdatum**. När du anger alternativet **Visa förfallodatum och tillåt redigering** till **Ja**, visas dialogrutan **uppdatera betalningsinformation**.  För att uppdatera befintliga transaktioner omedelbart, välj **uppdatera alla befintliga transaktioner**. Alternativt kan du också fylla i fälten för nya transaktioner genom att välja **Fortsätt utan uppdatering**.

Förfallodatumet läggs nu till på listsidan **leverantörstransaktioner** och blir det lättare ändra förfallodatum och kassarabattdatum för transaktioner.

### <a name="modify-the-payment-settings"></a>Ändra inställningar för betalning

Listsidan **leverantörstransaktioner** visar alla transaktioner för en leverantör. En dialogruta visas när du väljer förfallodatum för en transaktion. Den här dialogrutan visar basdatum för förfallodatum och beräkning av rabatter, förfallodatum, betalningsvillkor, kassarabattsvillkor och datum för kassarabatten.

Varje fält har en annan effekt på transaktionen vid redigering:

- **Redigera basdatum** – Förfallodagen och rabattdatumet ändras som om basdatumet är dokumentdatumet.
- **Redigera förfallodatum** – Endast förfallodatumet ändras
- **Redigera rabattdatum** – Endast rabattdatum ändras.
- **Redigera betalningsvillkoren** – Förfallodatumet ändras utifrån basdatum och betalningsvillkoren.
- **Redigera villkoren för kassarabatt** – Kassarabatterna ändras utifrån basdatum och kassarabattsvillkoren.

När du är klar med redigeringen av betalningdinställningar väljer du **Stäng** att spara dina ändringar.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]