---
title: Visa ordermeddelanden i POS
description: Det här avsnittet beskriver hur du aktiverar ordermeddelanden i POS och ramverket för meddelanden.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: c3b8e2774a189f2afefa757e7c4f3885b674918c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976798"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Visa ordermeddelanden i POS

[!include [banner](includes/banner.md)]

I dagens moderna butiksmiljö tilldelas butikens personal olika uppgifter, till exempel att hjälpa kunder, registrera transaktioner, lagerinventeringar och ta emot order i butiken. Kassaklienten ger en enda applikation där medarbetare kan utföra alla dessa uppgifter och många andra. Eftersom olika aktiviteter måste utföras under dagen kan personalen behöva meddelas när något kräver deras uppmärksamhet. Ramverket för meddelanden i POS hjälper till genom att låta återförsäljarna konfigurera rollbaserade meddelanden. Från och med Dynamics 365 for Retail med programuppdatering 5, kan dessa meddelanden konfigureras för kassaoperationer.


Systemet kan för närvarande endast visa meddelanden för orderuppföljningsåtgärder. Men eftersom ramverket är utformat till att vara utbyggbart kommer utvecklare så småningom kunna skriva en meddelandehanterare för alla åtgärder och visa meddelanden för den åtgärden i POS.

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Aktivera meddelanden för utförande av orderuppfyllelse

Om du vill aktivera meddelanden för utförande av orderuppfyllelse, se följande steg:

1. Navigera till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassa** &gt; **Åtgärder**.
2. Sök efter åtgärden **Orderuppfyllelse** och markera kryssrutan **Aktivera meddelanden** för att ange att ramverket för meddelanden ska lyssna på hanteraren för den här åtgärden. Om hanteraren implementeras visas meddelanden för den här åtgärden i POS.
3. Gå till **Butik och handel** &gt; **Medarbetare** &gt; **Medarbetare** &gt;, under fliken Commerce, öppna de kassabehörigheter som är kopplade till medarbetaren. Expandera snabbfliken **meddelanden**, lägg till åtgärden **orderuppfyllande** och ange fältet **visningsordning** till **1**. Om fler än ett meddelande har konfigurerats används det här fältet för att ordna meddelanden. Meddelanden som har ett lägre värde för **visningsordning** visas ovanför de meddelanden som har ett högre värde. Meddelanden som har ett värde för **visningsordning** av **1** visas överst.

    Meddelandena visas endast för åtgärder som läggs till på snabbfliken **meddelanden** och du kan bara lägga till åtgärder där om kryssrutan **Aktivera meddelanden** för dessa åtgärder är markerad på sidan **Kassaåtgärder**. Dessutom visas meddelanden för en åtgärd för medarbetare endast om åtgärden läggs till i kassabehörigheterna för dessa medarbetare.

    > [!NOTE]
    > Meddelanden kan åsidosättas på användarnivå. Öppna medarbetarens post, markera **Kassabehörigheter** och redigera sedan användarens meddelandeabonnemang.

4. Gå till **Butik och handel** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassaprofiler** &gt; **Funktionsprofiler**. I fältet **meddelandeintervall**, anger du hur ofta meddelanden ska dras. För vissa meddelanden måste POS ringa samtal i realtid till backoffice-programmet. Dessa samtal tar upp datorkapacitet i backoffice-programmets. Därför när du anger meddelandeintervallet bör du både beakta ditt företags behov och effekten av samtal i realtid till backoffice-programmet. Värdet **0** (noll) stänger av meddelandefunktionen.
5. Gå till **Butik och handel** &gt; **Butik och handel-IT** &gt; **Distributionsschema**. Välj schemat **1060** (**Personal**) för att synkronisera inställningar av meddelandeabonnemang och välj sedan **Kör nu**. Välj sedan schemat **1070** (**kanalkonfiguration**) för att synkronisera behörighetsintervallet och välj sedan **Kör nu**.

## <a name="view-notifications-in-the-pos"></a>Visa meddelanden i POS

När du har slutfört föregående steg ska medarbetare kunna visa meddelanden i POS. För att visa meddelanden, tryck på meddelandeikonen i det övre högra hörnet av POS. Ett meddelandecenter visas och visar meddelanden för utförandet av orderuppfyllelse. Meddelancecentret ska visa följande grupper inom utförandet av orderuppfyllelse:

- **Upphämtning i butik** Den här gruppen visar antalet order som har leveranssättet **upphämtning** och upphämtning kommer från den aktuella butiken. Du kan trycka på numret i gruppen så öppnas sidan **orderuppfyllelse**. I det här fallet filtreras sidan så att den endast visar de aktiva order som har ställts in för upphämtning från den aktuella butiken.
- **Leverera från butik** Den här gruppen visar antalet order som har leveranssättet **Leverans** och leverans är planerad från den aktuella butiken. Du kan trycka på numret i gruppen så öppnas sidan **orderuppfyllelse**. I det här fallet filtreras sidan så att den endast visar de aktiva order som har ställts in för försändelse från den aktuella butiken.

När nya order tilldelats butiken för uppfyllelse kommer meddelandeikonen att ändras för att indikera att det finns nya meddelanden och antalet för lämpliga grupper uppdateras. Även om grupperna uppdateras med jämna mellanrum kan kassaanvändare uppdatera grupperna manuellt när som helst genom att välja knappen **uppdatera** bredvid gruppen. Slutligen, om en grupp har en ny artikel som den aktuella medarbetaren inte har sett visar gruppen en explosionsikon som indikerar nytt innehåll.

## <a name="enable-live-content-on-pos-buttons"></a>Aktivera levande innehåll på kassaknappar

Kassaknapparna kan nu visa ett antal för att hjälpa medarbetarna att bestämma vilka aktiviteter som kräver deras omedelbara uppmärksamhet. För att visa detta nummer på en kassaknapp måste du slutföra de meddelandeinställningar som beskrivs tidigare i det här avsnittet (det vill säga du måste aktivera meddelanden för en åtgärd, konfigurera intervall för ett meddelande och uppdatera kassabehörighetsgrupp för medarbetaren). Dessutom måste du öppna knappsatsen för designern, visa knappens egenskaper och markera kryssrutan **Aktivera levande innehåll**. I fältet **Innehållsjustering** kan du välja om numret ska visas i det övre högra hörnet på knappen (**Högst upp till höger**) eller i mitten (**Mitten**).

> [!NOTE]
> Det levande innehållet kan endast aktiveras för åtgärder om kryssrutan **Aktivera meddelanden** har markerats för dem på sidan **Kassaåtgärder** som beskrivs tidigare i detta avsnitt.

Följande bild visar inställningarna för levande innehåll i knappsatsen för designern,

![Inställningar för levande innehåll i knappsatsens designer](./media/ButtonGridDesigner.png "Inställningar för levande innehåll i knappsatsens designer")

Om du vill visa meddelanderäkningen på en knapp måste du kontrollera att rätt skärmlayout håller på att uppdateras. Om du vill ta reda på vilken skärmlayout som används i POS väljer du ikonen **Inställningar** i övre högra hörnet och noterar **Skärmlayout-ID** och **Layoutupplösning.** Nu använder du Edge-webbläsaren, gå till sidan **skärmlayout**, leta reda på **bildskärms-ID** och **Layoutupplösning** som identifieras ovan och markera kryssrutan **Aktivera live-innehåll**. Gå **Butik och handel \> Butiken och handel-IT \> Distributionsschema** och kör 1090-jobbet (journaler) för att synkronisera layoutändringar.


![Hitta den skärmlayout som används i POS](./media/Choose_screen_layout.png "Hitta skärmlayouten")

Följande bild visar effekterna av att välja **Högst upp till höger** jämfört med **Mitten** i fältet **Innehållsjustering** för knappar med olika storlekar.

![Levande innehåll på kassaknappar](./media/ButtonsWithLiveContent.png "Levande innehåll på kassaknappar")


[!INCLUDE[footer-include](../includes/footer-banner.md)]