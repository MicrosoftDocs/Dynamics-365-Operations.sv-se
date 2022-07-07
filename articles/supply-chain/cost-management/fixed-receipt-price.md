---
title: Fast inleveranspris
description: I denna artikel beskrivs hur du kan konfigurera och använda fasta inleveranspriser i Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: d58e8dcc580bf9327cd89427530f59340e27f4aa
ms.sourcegitcommit: 78576abe5c7cbab1bb69d26c999b038e8c24873a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954704"
---
# <a name="fixed-receipt-price"></a>Fast inleveranspris

[!include [banner](../includes/banner.md)]

**Fast inleveranspris** är ett alternativ som du kan välja för en artikelmodellgrupp när du använder en annan lagermodell än *Standardkostnad* eller *Flytta viktat medelvärde*. I tidiga versioner av Microsoft Dynamics AX fick det här alternativet namnet **Standardkostnad**. Det ändrades till **Fast inleveranspris** när den nya lagermodellen för standardkostnad infördes i Dynamics AX 2012. I denna artikel beskrivs hur du kan konfigurera och använda fasta inleveranspriser i Dynamics 365 Supply Chain Management.

## <a name="about-fixed-receipt-prices"></a>Om fasta inleveranspriser

När du markerar kryssrutan **Fast inleveranspris** på sidan **Artikelmodellgrupp** för en artikel, använder systemet inleveranspris som standardkostnad för lagerinleveransen. Om inköpspriset och standardvarans självkostnadspris som är konfigurerat för en produkt skiljer sig åt, bokförs skillnaden till kontona **Fast inleveransprisvinst** eller **Fast inleveransprisförlust** och motbokas till **Motkonto för fast inleveranspris** som du anger på sidan **Bokföringsprofil för lager**.

Eftersom alternativet **Fast inleveranspris** används i samband med olika lagermodeller (som först in, först ut (FIFO); sist in, först ut (LIFO); och vägt medelvärde), processen *Lagerstängning och justering* kommer fortfarande att skapa avräkningar och justeringar enligt den inventeringsprincip som du väljer på sidan **Artikelmodellgrupp**. Justeringar görs dock endast för utleveranser från lager.

Du har till exempel konfigurerat en produkt med en artikelmodellgrupp där fältet **Lagermodell** ställs in på *FIFO* och alternativet **Fast inleveranspris**. När du tar emot lager genom en inköpsorder ställs lagervärdet in på värdet för artikelns standardsaldo vid inleverans av produkten. När du fakturerar inköpsordern bokför systemet standardsaldot på den frisläppta produkten på lagerkontot, om fakturapriset inte är det samma. Differensen bokförs på det fasta inleveransprisets vinst- eller förlustkonto. Senare, när du säljer eller använder produkten, använder systemet det löpande medelvärdet för artikeln vid den tidpunkt då försäljningsorderfakturan bokfördes (såvida du inte använder markering).

När du kör processen *Lagerstängning och justering* skapar systemet en avräkning med den första emissionen mot första kvittot. Skillnaden mellan inleveranspriset som användes på inleveransen och det löpande medelvärdet som användes för utleveransen bokförs i en ny verifikation.

## <a name="enable-fixed-receipt-prices"></a>Aktivera fasta inleveranspriser

Aktivera fasta inleveranspriser för en artikel genom att följa dessa steg.

1. Gå till **Lagerhantering \> Inställningar \> Lager \> Modellgrupper för artiklar**.
2. Skapa en ny artikelmodellgrupp eller välj en befintlig modellgrupp.
3. På snabbfliken **Kostnadsredovisningsmetod och kostnadsredovisning**, markera kryssrutan **Fast inleveranspris**.

    > [!NOTE]
    > Du kan inte markera kryssrutan **Fast inleveranspris** om fältet **Lagermodell** anges till *Standardkostnad* eller *Glidande medelvärde*.

4. Stäng sidan.

När du har aktiverar alternativet **Fast inleveranspris** måste du uppdatera lagerbokföringsprofilen genom att följa stegen nedan.

1. Gå till **Lagerhantering \> Inställningar \> Bokföring \> Bokföring**.
1. På fliken **Inköpsorder** i kolumnen **Välj**, markera **Fast inleveransprisvinst**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.
1. Ställ in den nya raden så att den gäller för artikelmodellgruppen som du aktiverar fast inleveransprissättning för, och ange huvudkontot som används för att registrera fasta inleveransprisvinster för inköpsorder. Konfigurera andra inställningar som du behöver.
1. I kolumnen **Välj**, märk **Fast inleveransprisförlust**. Lägg till en ny rad så att den gäller för artikelmodellgruppen som du aktiverar fast inleveransprissättning för, och ange huvudkontot som används för att registrera fasta inleveransprisförluster för inköpsorder. Konfigurera andra inställningar som du behöver.
1. I kolumnen **Välj**, märk **Motkonto för fast inleveranspris**. Lägg till en ny rad så att den gäller för artikelmodellgruppen som du aktiverar fast inleveransprissättning för, och ange huvudkontot som används för att registrera motkonto för fast inleveranspris för inköpsorder. Konfigurera andra inställningar som du behöver.
1. På fliken **Lager** i kolumnen **Välj**, markera **Fast inleveransprisvinst**. Lägg till en ny rad så att den gäller för artikelmodellgruppen som du aktiverar fast inleveransprissättning för, och ange huvudkontot som används för att registrera fasta inleveransprisvinster för lager. Konfigurera andra inställningar som du behöver.
1. I kolumnen **Välj**, märk **Fast inleveransprisförlust**. Lägg till en ny rad så att den gäller för artikelmodellgruppen som du aktiverar fast inleveransprissättning för, och ange huvudkontot som används för att registrera fasta inleveransprisförluster för lager. Konfigurera andra inställningar som du behöver.

> [!NOTE]
> Vi rekommenderar vanligtvis att fälten **Fast inleveransprisvinst** och **Fast inleveransprisförlust** använda samma huvudkonto för både inköpsorder och lager.

> [!IMPORTANT]
> När du ändrar värdet i fältet **Pris** på snabbfliken **Hantera kostnader** på sidan **Frisläppta produkter**, omvärderar inte systemet automatiskt det lager som finns till hands. Som en manuell lösning öppnar du sidan **Stängning och justering** och väljer **Justering \> Behållning** i åtgärdsfönstret. Välj sedan de artiklar som finns i behållning och justera dem till det aktuella priset. En klar fördel med att använda lagermodellen för standardkostnad är att den gör att systemet automatiskt omvärderar lagerbehållningen.
