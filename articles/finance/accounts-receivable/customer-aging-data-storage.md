---
title: Datalagring för kunders åldersfördelning
description: I det här avsnittet beskrivs hur du använder extern lagring för åldersdata för kunder. Du kan köra processen för lagring av åldersdata för kunder för att göra utdata tillgängliga för export till ett externt system.
author: JodiChristiansen
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ecd4f5359019e3c4778e21cc4946b9998cd519f
ms.sourcegitcommit: 9f8da0ae3dcf3861e8ece2c2df4f693490563d5e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/16/2021
ms.locfileid: "7817432"
---
# <a name="customer-aging-data-storage"></a>Datalagring för kunders åldersfördelning

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs hur du använder extern lagring för åldersdata för kunder. I Microsoft Dynamics 365 Finance kan du köra processen för lagring av åldersdata för kunder för att göra utdata tillgängliga för export till ett externt system. När du kör processen blir samma åldersrapportalternativ som finns tillgängliga i systemet tillgängliga för externa system. Detaljerna inkluderas alltid i exporterade data.

Det kan vara praktiskt att göra kundernas åldersdata tillgängliga i ett externt system för lagring i fall där utleveransen innehåller många kunder och/eller många transaktioner. Om den befintliga **åldersfördelningsrapporten för kunder** går ut på grund av att den innehåller för mycket data att skriva ut, är denna funktion ett alternativt sätt att hämta samma data.

## <a name="enable-the-customer-aging-data-storage-feature"></a>Aktivera funktionen för datalagring för kunders åldersfördelning

Innan du kan använda den här funktionen måste du aktivera den i ditt system. Administratörer kan använda inställningarna funktionshantering för att kontrollera funktionens status och aktivera den om det behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** kredit och inkasso
- **Funktionens namn:** Datalagring för kunders åldersfördelning

## <a name="run-the-customer-aging-data-storage-process"></a>Kör processen för datalagring för kunders åldersfördelning

1. Gå till **Kredit och inkasso \> Förfrågningar och rapporter \> Kund \> Datalagring för kunders åldersfördelning**.
2. Välj **Ny**.
3. Ange ett namn för processen i fältet **Namn**.
4. Ställ in de återstående parametrarna efter behov.

    > [!NOTE]
    > Transaktionsdetaljer inkluderas alltid och bearbetningen utförs alltid i ett batchjobb.

5. Välj **OK**.
6. Uppdatera sidan **Datalagring för kunders åldersfördelning** att se värdena **Batchnamn** och **Batch körtid** som visas tillsammans med värdet **Bearbetningsstatus**. När batchjobbet är slutfört ställs fältet **Bearbetningsstatus** in på **Avslutad** och fältet **Antal åldersrader** anges. Om batchjobbet är återkommande ställs fältet **Bearbetningsstatus** in på **Väntar**.
7. Välj knappen **Filter** bredvid fältet **Antal åldersrader** om du vill granska filtren som har lagts till för batchjobbet.

Sidan **Datalagring för kunders åldersfördelning** omfattar inte resultaten. Med hjälp av dataenheten **Datalagring för kunders åldersfördelning** kan du dock exportera utdata till de format som Datahantering har stöd för.

> [!NOTE]
> Innan du exporterar lägger du till ett filter för att begränsa det exporterade resultatet till det senaste åldersfördelningen. Lägg till exempel till följande kriterier när du vill returnera den senaste batchkörningen:
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchName())
>
> Alternativt lägger du till följande kriterier när du vill returnera den senaste batchkörningen för den nuvarande användaren:
>
> (CustAgingDataStorageSysQueryRangeUtil::getLatestBatchNameForCurrentUser())