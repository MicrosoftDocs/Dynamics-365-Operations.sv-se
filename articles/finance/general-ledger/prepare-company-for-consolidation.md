---
title: Förbereda en juridisk person för konsolideringsprocessen
description: I samband med en konsolidering samlas transaktioner in från flera uppsättningar konton för juridiska personer till en enda uppsättning av konton för juridiska personer. I denna artikel beskrivs hur du förbereder en juridisk person för en konsolidering.
author: jinniew
ms.date: 10/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: 2a3d4645c79ec30df2bbb7a32a82a59fdb7016e5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894038"
---
# <a name="prepare-a-legal-entity-for-the-consolidation-process"></a>Förbereda en juridisk person för konsolideringsprocessen

[!include [banner](../includes/banner.md)]

I samband med en konsolidering samlas transaktioner in från flera uppsättningar konton för juridiska personer till en enda uppsättning av konton för juridiska personer. I denna artikel beskrivs hur du förbereder en juridisk person för en konsolidering.

> [!NOTE]
> Vi rekommenderar att du använder Management Reporter för Microsoft Dynamics 365 Finance för att kombinera ekonomiska resultat för flera juridiska personer i ett konsoliderat format. I Management Reporter kan du skapa konsoliderade ekonomiska rapporter för juridiska personer, använda Excel för att importera konsolideringsdata från andra källor, samt översätta belopp till valfritt antal rapporteringsvalutor utan att behöva köra konsolideringsprocessen i Dynamics 365 Finance.

Du kan skriva ut rapporter, till exempel bokslut, från den konsoliderade juridiska personen. Du kan dock inte använda den konsoliderade juridiska personen för dagliga transaktioner.

Du kan konsolidera data från juridiska personer som använder andra databaser än databasen för den konsoliderade juridiska personen. Denna konsolideringsprocess kallas för en *importkonsolidering*. Alternativt kan de juridiska personerna använda samma databas som den konsoliderade juridiska personen. Denna konsolideringsprocess kallas för en *onlinekonsolidering*.

Den konsoliderade juridiska personen samlar in resultat och saldon för dotterbolagen. För att förbereda en konsoliderad juridisk person för en konsolidering måste du göra följande:

1. Gå till **Redovisning \> Inställningar \> Organisation \> Juridiska personer**.
2. Välj **Ny** för att skapa den juridiska person som ska utgöra konsoliderande juridisk person.
3. Markera kryssrutan **Använd för ekonomisk konsolideringsprocess** och ange sedan information om den konsoliderade juridiska entiteten. Se till att ange följande information exakt så som du vill att den ska visas i bokslut för den konsoliderade juridiska personen.
4. Stäng sidan.
5. Välj den konsoliderade juridiska personen i fältet i sidans övre högra hörn och välj sedan **OK**.
6. Gå till **Redovisning \> Inställningar \> Redovisning**.
7. Välj kontoplanen, räkenskapskalendern, redovisningsvalutan, en valfri rapportvaluta och standardvalutakursen för den konsoliderade juridiska personen. 
8. Gå till **Redovisning \> Inställningar \> Valuta \> Valutakurser**.
9. Ställa in valutakurser i relevanta perioder för valutor i juridiska personer för dotterbolag.
10. Stäng sidan.
11. Om den konsoliderade juridiska personen har dotterbolag som använder utländska valutor följer du dessa steg:

    1. Gå till **Redovisning \> Inställningar \> Bokföring \> Konton för automatiska transaktioner**.
    2. I fältet **Bokföringstyp** väljer du ett lämpligt konto:

        - Om den juridiska personen har utländska dotterbolag som är ekonomiskt eller verksamhetsmässigt ömsesidigt beroende av den överordnade juridiska personen, ska du välja ett lämpligt konto för bokföringstypen **Vinst- och förlustkonto för konsolideringsdifferenser**.
        - Om du konsoliderar ett dotterbolag som är ekonomiskt och verksamhetsmässigt oberoende av den överordnade juridiska personen, eller en juridisk person som innehåller resultaten från flera dotterbolag som är ekonomiskt och verksamhetsmässigt oberoende av den överordnade juridiska personen, och om du använder konverteringsmetoder för konsolidering av data, ska du välja ett lämpligt konto för bokföringstypen **Saldokonto för konsolideringsskillnader**.

    3. I fältet **Huvudkonto** väljer du det huvudkonto som ska användas för justeringar av omräkning i utländsk valuta.
    4. Stäng sidan.

    Om du skapar den konsoliderade juridiska personen tidigt under perioden kan du omvärdera de utländska valutabeloppen som valutakursändringar under konsolideringsperioden.

Den konsoliderade juridiska personen har nu ställts in för det periodiska jobbet **Konsolidera**. Du kan antingen göra en importkonsolidering eller en onlinekonsolidering.

- Om du vill göra en importkonsolidering går du till **Redovisning \> Periodisk \> Konsolidera \> Konsolidera \[Importera från\]**.
- Om du vill göra en onlinekonsolidering går du till **Redovisning \> Periodisk \> Konsolidera \> Konsolidera \[Online\]**.

> [!NOTE]
> Innan du kan bearbeta konsolideringen måste du förbereda dotterbolagens juridiska personer för konsolidering. Mer information finns i [Skapa en juridisk person för dotterbolag för konsolidering](set-up-subsidiary-company-for-consolidation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
