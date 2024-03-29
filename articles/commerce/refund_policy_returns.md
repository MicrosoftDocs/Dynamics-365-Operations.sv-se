---
title: Skapa och uppdatera en retur- och återbetalningspolicy för en kanal
description: I denna artikel beskrivs hur du konfigurerar en policy för returer och återbetalningar för en kanal.
author: ShalabhjainMSFT
ms.date: 07/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.custom: ''
ms.search.industry: Retail
ms.openlocfilehash: d01ad490301dd2f4103b8bd3f702db12b93a45a8
ms.sourcegitcommit: bd7b1ffe90b25eb4c68d6aaebd063bf33e09d9cd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/05/2022
ms.locfileid: "9627507"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a>Skapa och uppdatera en retur- och återbetalningspolicy för en kanal

[!include [banner](includes/banner.md)]

Med hjälp av en returpolicy för en kanal i Dynamics 365 Commerce kan återförsäljare ange vilka betalningsmedel som kan tillåtas att bearbeta en retur i en kassa.  

I denna artikel beskrivs hur du konfigurerar en policy för returer och återbetalningar för en kanal.

Omfattningen av policyn är för närvarande begränsad till att konfigurera betalningsmedel som kan tillåtas för en kanal. Listan tillåtna är baserad på de betalsätt som används för att göra inköpet. Exempel:

- Om ett inköp gjorts med hjälp av ett presentkort, är butikens policy att endast bearbeta återbetalningar till ett nytt presentkort eller för att ge butikskredit. 
- Om en försäljning görs med kontanter är de alternativ som är tillåtna för återbetalning det kontanter, presentkort och kundkonto, men inte kreditkort. 

## <a name="enable-return-policy"></a>Aktivera returpolicy

Den här funktionen är aktiverad som standard. Du hittar den i arbetsytan **Funktionshantering** genom att söka efter **Aktivera policyer för kanalretur** i listan med funktionsnamn.


## <a name="configure-return-policy"></a>Konfigurera returpolicy

Följ stegen nedan när du vill konfigurera en returpolicy för en butikskanalen eller online butikskanal.

1. Gå till **Butik och handel** \> **Kanalinstallation** \> **Returer** \> **Returpolicy för kanal**.

1. Välj **Ny** om du vill skapa en ny returpolicy för butikens öppettider. Om du vill använda en befintlig mall väljer du mallen i det vänstra fönstret. För nya mallar lägger du till ett namn och en beskrivning som gör det enklare att identifiera principen när den tillämpas på kanalen.

   ![Lägg till ny returpolicy.](media/Return-policy-page1.png)
     
   
1. I avsnittet **tillåtna betalsätt** för bidrag kan du definiera **tillåtna** returavgifter som är specifika för varje betalningsmetod.
   ![Ange tillåtna betalsätt per betalningstyp.](media/Return-policy-page2.png)
   
    > [!IMPORTANT]
    > - Betalsätten härleds från de betalsätt som har ställts in för organisationen.
    > - Om du lägger till en betalningsmedeltyp som är tillåten för varje listad betalningsmetod kan returer göras av den tillåtna betalningsmedelstypen för retur.
    
1. Associera returpolicymallen för öppettider med butikerna där den ska användas. Välj **Lägg till** på fliken **Butikskanaler** och koppla de tillgängliga kanalerna. 

    - I dialogrutan **Välj organisationsnoder** väljer du butiker, regioner och organisationer som mallen ska associeras med.
    - Det går bara att associera en returpolicymall till varje butik.
    - Välj butiker, regioner eller organisationer med pilknapparna.
    - Giltighetsdatumet för policyn är det datum då policyn tillämpas på kanalerna och kanaljobben körs. 

    ![Dialogrutan Välj organisationsnoder.](media/Return-policy-page3.png)

1. På sidan **distributionsschema** kör du jobbet **1070** för att göra returpolicy för kanal tillgänglig för POS.

## <a name="preview-the-channel-return-policy-in-the-pos"></a>Förhandsgranska returpolicy för kanal i POS

Följ stegen i något av följande exempel för att visa de tillåtna betalningsmedelstyperna för retur i POS.

1. Logga in i POS som kassör eller chef.
1. Under **skift och kassalåda**, välj **visa journal**.
1. Välj den transaktion som ingår i returen. 
1. Markera artiklarna som ska återbetalas och välj betalningsmetod.  
    - Om betalningsmedel har valts i listan tillåten betalningsmedelstyper kan kassören slutföra transaktionen.
    - Om betalningsmedel väljs ej är tillåtet visas ett felmeddelande.
    - Välj **belopp som förfaller** för att visa en lista med alla tillåtna typer av returbetalningsmedel.

- eller -

1. Logga in i POS som kassör eller chef.
1. Välj **returtransaktion** och ange kvitto-ID:t med en streckkodssökning eller per manuell inmatning. 
1. Välj den transaktion som ingår i returen. 
1. Markera artiklarna som ska återbetalas och välj betalningsmetod.  
    - Om betalningsmedel har valts i listan tillåten betalningsmedelstyper kan kassören slutföra transaktionen.
    - Om betalningsmedel väljs ej är tillåtet visas ett felmeddelande.
    - Välj **belopp som förfaller** för att visa en lista med alla tillåtna typer av returbetalningsmedel.

![Återbetalningstypen tillåts inte.](media/Return-policy-page6.png)



![Återbetalningstyper tillåtna.](media/Return-policy-page5.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
