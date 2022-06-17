---
title: Ändra redovisnings- eller rapporteringsvaluta
description: Den här artikeln förklarar hur du ändrar redovisnings- eller rapporteringsvalutan eller lägger till en rapporteringsvaluta i redovisningsinställningarna.
author: kweekley
ms.date: 05/05/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-05-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b02432c8e0bdf52c2a588f67a581b78e682b1bf8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904626"
---
# <a name="change-the-accounting-or-reporting-currency"></a>Ändra redovisnings- eller rapporteringsvaluta

[!include [banner](../includes/banner.md)]

Den här artikeln förklarar hur du ändrar redovisnings- eller rapporteringsvalutan eller lägger till en rapporteringsvaluta i redovisningsinställningarna.

## <a name="symptom"></a>Symtom

Du vill ändra redovisnings- eller rapporteringsvalutan eller lägger till en rapporteringsvaluta i redovisningsinställningarna. Det här inträffar vanligen i följande scenarier:

- Fel redovisnings- eller rapporteringsvaluta angavs när en juridisk person konfigurerades. Nu vill du ändra den valutan.
- En rapporteringsvaluta angavs när en juridisk person konfigurerades, men organisationen vill nu ta bort rapporteringsvalutan.
- Organisationen uppgraderar eller migrerar till Microsoft Dynamics 365 Finance och vill ändra redovisnings- eller rapporteringsvalutan.

En organisation som inte använder funktionen Dubbla valutor vill börja använda den. Det här problemet inträffar vanligen i följande scenarier.

- Ingen rapporteringsvaluta angavs när en juridisk person konfigurerades. (Rapporteringsvaluta är valfritt.) Nu vill du lägga till en rapporteringsvaluta.

## <a name="resolution"></a>Lösning

Det viktigaste att fundera på är om några transaktioner (faktiska eller budget) har bokförts i den juridiska personen för redovisningsinställningarna. **Det går inte att ändra redovisnings- eller rapporteringsvalutan eller lägga till en rapporteringsvaluta om transaktioner (faktiska eller budget) har bokförts i den juridiska personen.** Följ stegen i något av följande avsnitt, beroende på om transaktioner har bokförts.

### <a name="no-transactions-have-been-posted"></a>Inga transaktioner har bokförts

1. Öppna **Redovisning \> Redovisningsinställningar \> Redovisning** i den juridiska person vars valutor du uppdaterar.
2. Välj **Redigera** på sidan **Redovisning**.
3. Välj redovisnings- och rapporteringsvaluta att använda för den juridiska personen på snabbfliken **Valuta**.
4. Välj **Spara**.

Om fälten för redovisnings- och rapporteringsvalutan inte finns tillgängliga på sidan **Redovisning** har en eller flera transaktioner (faktiska eller budget) bokförts i den juridiska personen. Därför går det inte att ändra valutorna. Följ i stället stegen i nästa avsnitt.

### <a name="transactions-have-been-posted"></a>Transaktioner har bokförts

**Det enda sättet att ändra eller lägga till redovisnings- och rapporteringsvalutor om transaktioner har bokförts i den juridiska personen, är att skapa en ny juridisk person med rätt valutor.** För att underlätta den här processen kan datahantering i systemet kopiera installationsposter och huvudposter från den aktuella juridiska personen till en ny juridisk person.

Ändringar i redovisnings- och rapporteringsvalutorna är genomgripande. De påverkar inte bara redovisningen utan även varje underleverantör (kundreskontra, leverantörsreskontra, lager, projekt och så vidare), alla ISV-lösningar (Independent Software Vendor) och alla tillägg som du har gjort som lagrar belopp.

Processen att hitta och översätta varje belopp till en annan valuta är föremål för fel. Därför godkänner inte teknikerteamet ett skript som ändrar eller lägger till redovisnings- och rapporteringsvalutor. Även om ett verktyg som tidigare var tillgängligt för Microsoft Dynamics AX 2012 gör det möjligt att ändra eller lägga till redovisnings- och rapporteringsvalutor, är det verktyget inaktuellt för både AX 2012 R3 och Finance.

Följ dessa steg för att kopiera inställnings- och huvuddata från den aktuella juridiska personen till en ny juridisk person.

1. Gå till **Arbetsytor \> Datahantering**.
2. Välj **Mallar** under gruppen **Importera/exportera**.
3. Kontrollera att mallar finns tillgängliga. Om det inte finns mallar, välj **Läs in standardmallar** och vänta på att mallarna skapas.
4. Återgå till arbetsytan **Datahantering**.
5. Välj **Kopiera till juridisk person**.
6. Ange ett namn och en beskrivning för gruppen.
7. Välj den juridiska personen som du vill kopiera data från i fältet **Juridisk person, källa**.
8. Välj **Skapa juridiska personer** på snabbfliken **Destinationens juridiska person** för att skapa en ny juridisk person till vilken du kopierar data från källans juridiska person. Välj **Välj befintlig** om du vill kopiera data till en befintlig juridisk person.
9. Valfritt: Ställ in fältet **Kopiera nummerserier** på **Ja**. (Vi rekommenderar det här steget när du kopierar data.)
10. Välj **Lägg till mall** i området **Valda entiteter**.
11. Välj mallar att använda. Föreslagna mallar för en ny juridisk person inkluderar **025 - Redovisning** och **Ekonomi**. Vi rekommenderar att du granskar alla andra tillgängliga mallar för att avgöra om någon av dem gäller för dina krav.
12. Välj **Kopiera till juridisk person** om du vill starta en batchprocess som skapar de valda enheterna och kopierar dem till målets juridiska person.
13. När processen är klar måste du innan transaktioner bokförs gå till redovisningen och uppdatera redovisnings- och rapporteringsvalutorna enligt beskrivningen tidigare i den här artikeln.

Om du skapade en ny juridisk person för att ändra redovisnings- eller rapporteringsvalutan måste du kontrollera att startsaldon omräknas från den gamla juridiska personens valutor till de nya valutorna.

En video som visar föregående steg finns i [Kopiera till juridisk person](https://community.dynamics.com/365/b/techtalks/posts/copy-into-legal-entity-october-24-2017).
