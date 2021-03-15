---
title: Skapa och uppdatera ett retur- och återbetalningspolicy för en kanal
description: I det här avsnittet beskrivs hur du ställer in en policy för returer och återbetalningar för en kanal.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 89e8fe78414e73053317ebe19e3afcc89231d440
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979733"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a>Skapa och uppdatera ett retur- och återbetalningspolicy för en kanal

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Översikt

Med hjälp av en returpolicy för en kanal i Dynamics 365 Commerce kan återförsäljare ange vilka betalningsmedel som kan tillåtas att bearbeta en retur i en kassa.  

I det här avsnittet beskrivs hur du ställer in en policy för returer och återbetalningar för en kanal.

Omfattningen av policyn är för närvarande begränsad till att ställa in betalningsmedel som kan tillåtas för en kanal. Listan tillåtna är baserad på de betalsätt som används för att göra inköpet. Exempel:

- Om ett inköp gjorts med hjälp av ett presentkort, är butikens policy att endast bearbeta återbetalningar till ett nytt presentkort eller för att ge butikskredit. 
- Om en försäljning görs med kontanter är de alternativ som är tillåtna för återbetalning det kontanter, presentkort och kundkonto, men inte kreditkort. 


## <a name="enable-return-policy"></a>Aktivera returpolicy

Aktivera funktionen för att återgå till kanalen genom att göra följande:

1. Gå till arbetsytan **Funktionshantering** i Dynamics 365 Commerce.
2. Sök efter funktionen **aktivera kanal returprinciper** i listan med funktionsnamn.
3. Välj **Aktivera nu**. 

## <a name="configure-return-policy"></a>Konfigurera returpolicy

Följ stegen nedan när du vill konfigurera en returpolicy för en butikskanalen eller online butikskanal.

1. Gå till **Butik och handel** \> **Kanalinstallation** \> **Returer** \> **Returpolicy för kanal**.

2. Välj **Ny** om du vill skapa en ny returpolicy för butikens öppettider. Om du vill använda en befintlig mall väljer du mallen i det vänstra fönstret. För nya mallar lägger du till ett namn och en beskrivning som gör det enklare att identifiera principen när den tillämpas på kanalen.

   ![Lägg till ny returpolicy](media/Return-policy-page1.png "Lägg till ny returpolicy")
     
   
3. I avsnittet **tillåtna betalsätt** för bidrag kan du definiera **tillåtna** returavgifter som är specifika för varje betalningsmetod.
   ![Lägg till betalsätt](media/Return-policy-page2.PNG "Ange tillåtna betalsätt per betalningstyp")
   
    > [!IMPORTANT]
    > - Betalsätten härleds från de betalsätt som har ställts in för organisationen.
    > - Om du lägger till en betalningsmedeltyp som är tillåten för varje listad betalningsmetod kan returer göras av den tillåtna betalningsmedelstypen för retur.
    
4. Associera returpolicymallen för öppettider med butikerna där den ska användas. Välj **Lägg till** på fliken **Butikskanaler** och koppla de tillgängliga kanalerna. 

    - I dialogrutan **Välj organisationsnoder** väljer du butiker, regioner och organisationer som mallen ska associeras med.
    - Det går bara att associera en returpolicymall till varje butik.
    - Välj butiker, regioner eller organisationer med pilknapparna.
    - Giltighetsdatumet för policyn är det datum då policyn tillämpas på kanalerna och kanaljobben körs. 

    ![Dialogrutan Välj organisationsnoder](media/Return-policy-page3.PNG "Dialogrutan Välj organisationsnoder")

5. På sidan **distributionsschema** kör du jobbet **1070** för att göra returpolicy för kanal tillgänglig för POS.

## <a name="preview-the-channel-return-policy-in-the-pos"></a>Förhandsgranska returpolicy för kanal i POS

Följ stegen i något av följande exempel för att visa de tillåtna betalningsmedelstyperna för retur i POS.

1. Logga in i POS som kassör eller chef.
2. Under **skift och kassalåda**, välj **visa journal**.
3. Välj den transaktion som ingår i returen. 
4. Markera artiklarna som ska återbetalas och välj betalningsmetod.  
- Om betalningsmedel har valts i listan tillåten betalningsmedelstyper kan kassören slutföra transaktionen.
- Om betalningsmedel väljs ej är tillåtet visas ett felmeddelande.
- Välj **belopp som förfaller** för att visa en lista med alla tillåtna typer av returbetalningsmedel.

- eller -

1. Logga in i POS som kassör eller chef.
2. Välj **returtransaktion** och ange kvitto-ID:t med en streckkodssökning eller per manuell inmatning. 
3. Välj den transaktion som ingår i returen. 
4. Markera artiklarna som ska återbetalas och välj betalningsmetod.  
- Om betalningsmedel har valts i listan tillåten betalningsmedelstyper kan kassören slutföra transaktionen.
- Om betalningsmedel väljs ej är tillåtet visas ett felmeddelande.
- Välj **belopp som förfaller** för att visa en lista med alla tillåtna typer av returbetalningsmedel.

![Återbetalning tillåts inte](media/Return-policy-page6.png "Återbetalningstyp tillåts inte")



![Lista över betalsätt](media/Return-policy-page5.PNG "Återbetalningstyp tillåts")


[!INCLUDE[footer-include](../includes/footer-banner.md)]