---
title: Visa ordermeddelanden i POS
description: Det här avsnittet beskriver hur du aktiverar ordermeddelanden i POS och ramverket för meddelanden.
author: ShalabhjainMSFT
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 57f5d23533c2fd17593648a15745fa770fc01dc4
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345218"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Visa ordermeddelanden i POS

[!include [banner](includes/banner.md)]

Butikspersonal kan ha olika uppgifter i butiken, till exempel att uppfylla order eller utföra lagerinleverans eller lagerinventering. Kassaklienten ger en enda applikation där medarbetare kan meddelas om dessa uppgifter. Ramverket för meddelanden i POS hjälper till genom att låta återförsäljarna konfigurera rollbaserade meddelanden. Med start i Dynamics 365 Retail med programuppdatering 5, kan dessa meddelanden konfigureras för kassaoperationer.

Systemet kan visa meddelanden för operationen *orderuppfyllelse* och startar i Commerce-version 10.0.18 meddelanden kan även visas för operationen *orderuppfyllelse*. Men eftersom ramverket är utformat för att vara utdragbart kan utvecklare göra det [skriva en meddelandehanterare](dev-itpro/extend-pos-notification.md) för alla operationer och visa meddelanden för den operationen i kassan.

## <a name="enable-notifications-for-order-fulfillment-or-recall-order-operations"></a>Aktivera meddelanden för utförande eller återkalla orderoperationer

Om du vill aktivera meddelanden för utförande av orderuppfyllelse, eller återkalla orderoperationer, följ dessa steg.

1. Gå till **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassa \> Åtgärder**.
1. Sök antingen efter åtgärden **Orderuppfyllelse** eller åtgärden **Återkalla order** och välj sedan **Aktivera meddelanden** för åtgärden att specificera att anmälningsramen ska lyssna på hanteraren för den här åtgärden. Om hanteraren implementeras visas meddelanden för den här åtgärden i POS.
1. Gå till **Retail och Commerce \> Medarbetare \> Arbetare**.
1. Välj fliken **Commerce**, välj en arbetarrad och **kassabehörigheter**. Markera snabbfliken **Meddelanden** om du vill utöka den och lägg sedan till de åtgärder som du har aktiverat meddelanden för. Om du konfigurerar ett enda meddelande till en arbetare måste värdet **Visningsorder** är inställt på **1**. Om du konfigurerar fler än en åtgärd ställer du in värdena för **visningsordning** för att ange i vilken ordning meddelandena ska visas. 

      Meddelanden visas bara för åtgärder som läggs till på snabbfliken **Meddelanden**. Du kan bara lägga till åtgärder där om **Aktivera meddelanden** för dessa åtgärder har markerats på sidan **kassaåtgärder**. Dessutom visas meddelanden för en åtgärd för medarbetare endast om åtgärden läggs till i kassabehörigheterna för dessa medarbetare.

    > [!NOTE]
    > Meddelanden kan åsidosättas på användarnivå. Öppna medarbetarens post, markera **Kassabehörigheter** och redigera sedan användarens meddelandeabonnemang.

1. Gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**. I fältet **meddelandeintervall**, anger du hur ofta meddelanden ska dras. För vissa meddelanden måste POS ringa samtal i realtid till backoffice-programmet. Dessa samtal tar upp datorkapacitet i backoffice-programmets. Därför när du anger meddelandeintervallet bör du både beakta ditt företags behov och effekten av samtal i realtid till backoffice-programmet. Värdet **0** (noll) stänger av meddelandefunktionen.
1. Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**. Välj schemat **1060** (**Personal**) för att synkronisera inställningar av meddelandeabonnemang och välj sedan **Kör nu**. Välj sedan schemat **1070** (**kanalkonfiguration**) för att synkronisera behörighetsintervallet och välj sedan **Kör nu**.

## <a name="view-notifications-in-the-pos"></a>Visa meddelanden i POS

När du har slutfört föregående steg ska medarbetare kunna visa meddelanden i POS. För att visa meddelanden, tryck på meddelandeikonen i det övre högra hörnet av POS. En meddelandepanel visas och visar meddelanden för de åtgärder som konfigurerats för arbetaren. 

För åtgärden **orderuppfyllelse** visar meddelandepanelen följande grupper:

- **Upphämtning i butik** – Den här gruppen visar antalet individuella orderrader som är schemalagda för upphämtning från den aktuella butiken. Du kan välja numret i gruppen som du vill öppna åtgärden **Orderuppfyllelse** med ett filter så att det bara visar de aktiva orderraderna som är inställda för hämtning från den aktuella butiken.
- **Leverera från butik** – I den här gruppen visas räkningen av enskilda orderrader som har konfigurerats att levereras från användarens aktuella butik. Du kan välja numret i gruppen som du vill öppna åtgärden **Orderuppfyllelse** med ett filter så att det bara visar de aktiva orderraderna som är inställda för leverans från den aktuella butiken.

För åtgärden **återkalla order** visar meddelandepanelen följande grupper:

- **Order som ska uppfyllas** – I den här gruppen visas antalet order som har konfigurerats för upphämtning eller leverans av användarens aktuella butik. Du kan välja numret i gruppen för att öppna åtgärden **Återkalla order** med en filtrerad vy som bara visar de öppna order som måste uppfyllas av användarens aktuella butik för antingen hämtning i butik eller leverans från butiksscenarier.
- **Order som ska hämtas** – Den här gruppen visar antalet order som är schemalagda för upphämtning från den aktuella butiken. Du kan välja numret i gruppen för att öppna åtgärden **Återkalla order** med en filtrerad vy som bara visar de öppna order som måste uppfyllas för kunden att hämta från användarens nuvarande butik..
- **Order som ska levereras** – I den här gruppen visas antalet order som ska levereras från användarens aktuella butik. Du kan välja numret i gruppen för att öppna åtgärden **Återkalla order** med en filtrerad vy som bara visar de öppna order som måste uppfyllas för leverans från användarens nuvarande butik..

För både orderuppfyllelse och återkallande orderaviseringar, eftersom nya order plockas upp av processen kommer meddelandeikonen att ändras för att indikera att det finns nya meddelanden och antalet för lämpliga grupper uppdateras. Även om grupperna uppdateras med jämna mellanrum kan kassaanvändare uppdatera grupperna manuellt när som helst genom att välja knappen **uppdatera** bredvid gruppen. Slutligen, om en grupp har en ny artikel som den aktuella medarbetaren inte har sett visar gruppen en explosionsikon som indikerar nytt innehåll.

## <a name="enable-live-content-on-pos-buttons"></a>Aktivera levande innehåll på kassaknappar

Kassaknapparna kan nu visa ett antal för att hjälpa medarbetarna att bestämma vilka aktiviteter som kräver deras omedelbara uppmärksamhet. För att visa detta nummer på en kassaknapp måste du slutföra de meddelandeinställningar som beskrivs tidigare i det här avsnittet (det vill säga du måste aktivera meddelanden för en åtgärd, konfigurera intervall för ett meddelande och uppdatera kassabehörighetsgrupp för medarbetaren). Dessutom måste du öppna knappsatsen för designern, visa knappens egenskaper och markera kryssrutan **Aktivera levande innehåll**. I fältet **Innehållsjustering** kan du välja om numret ska visas i det övre högra hörnet på knappen (**Högst upp till höger**) eller i mitten (**Mitten**).

> [!NOTE]
> Det levande innehållet kan endast aktiveras för åtgärder om kryssrutan **Aktivera meddelanden** har markerats för dem på sidan **Kassaåtgärder** som beskrivs tidigare i detta avsnitt.

Följande bild visar inställningarna för levande innehåll i knappsatsen för designern,

![Inställningar för levande innehåll i knappsatsens designer.](./media/ButtonGridDesigner.png "Inställningar för levande innehåll i knappsatsens designer")

Om du vill visa meddelanderäkningen på en knapp måste du kontrollera att rätt skärmlayout håller på att uppdateras. Om du vill ta reda på vilken skärmlayout som används i POS väljer du ikonen **Inställningar** i övre högra hörnet och noterar **Skärmlayout-ID** och **Layoutupplösning.** Nu använder du Edge-webbläsaren, gå till sidan **skärmlayout**, leta reda på **bildskärms-ID** och **Layoutupplösning** som identifieras ovan och markera kryssrutan **Aktivera live-innehåll**. Gå **Butik och handel \> Butiken och handel-IT \> Distributionsschema** och kör 1090-jobbet (journaler) för att synkronisera layoutändringar.

![Hitta den skärmlayout som används i kassan.](./media/Choose_screen_layout.png "Hitta skärmlayouten")

Följande bild visar effekterna av att välja **Högst upp till höger** jämfört med **Mitten** i fältet **Innehållsjustering** för knappar med olika storlekar.

![Levande innehåll på kassaknappar.](./media/ButtonsWithLiveContent.png "Levande innehåll på kassaknappar")

[!INCLUDE[footer-include](../includes/footer-banner.md)]
