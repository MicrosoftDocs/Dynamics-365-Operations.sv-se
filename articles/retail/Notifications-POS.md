---
title: Visa ordermeddelanden i kassan
description: "Det här avsnittet beskriver hur du aktiverar ordermeddelanden i kassan och ramverket för meddelanden som kan utökas till att omfatta andra åtgärder."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: a1206aea3f78246951581c1dc6338e39a0942ea2
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---

# <a name="display-notifications-in-point-of-sale"></a>Visa meddelanden i kassan

[!include[banner](includes/banner.md)]

I dagens moderna butiksmiljö tilldelas butikens personal olika uppgifter, till exempel att hjälpa kunder, registrera transaktioner, lagerinventeringar och ta emot order i butiken. Kassaklienten gör det möjligt för butikens personal att utföra dessa uppgifter och mycket mer, allt i ett enda program. Med olika aktiviteter som ska utföras under en dag kan personalen behöva meddelas när något kräver deras uppmärksamhet. Ramverket för meddelanden i kassan löser detta problem genom att låta återförsäljarna konfigurera rollbaserade meddelanden. Med Dynamics 365 for Retail med programuppdatering 5, kan dessa meddelanden bara konfigureras för kassaåtgärder.

För närvarande ger systemet möjligheten att visa meddelanden för utförande av orderuppfyllelse, men ramverket är utformat att kunna utökas så att utvecklare i framtiden kan skriva en meddelandehanterare för någon åtgärd och visa meddelanden i kassan.  

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Aktivera meddelanden för utförande av orderuppfyllelse

Om du vill aktivera meddelanden för utförande av orderuppfyllelse, se följande steg:

 - Gå till sidan **Åtgärder** (**Butik** > **Kanalinställningar** > **Kassainställningar** > **Kassa** > **Åtgärder**).
 - Sök efter utförande av orderuppfyllelse och markera kryssrutan **Aktivera meddelanden** för åtgärden. Detta indikerar att ramverket för meddelanden lyssnar på hanteraren för utförande av orderuppfyllelse. Om hanteraren är implementerad visas meddelanden i kassan, annars visas inte meddelanden för den här åtgärden.
- Gå till kassabehörigheterna som är kopplade till personalen under snabbfliken **meddelanden**, lägg till utförande av orderuppfyllelse med ”visningsordningen” 1. Om det finns fler än ett meddelande konfigurerats, används visningsordningen för att ordna meddelandet uppifrån och ned där 1 är högst upp. Endast dessa åtgärder kan läggas till för vilka kryssrutan **Aktivera meddelanden** har markerats. Dessutom visas meddelanden endast för de operationer som har lagts till här och enbart till operationer som har lagt till motsvarande kassabehörigheter. 

> [!NOTE]
> Meddelanden kan åsidosättas på användarnivå genom att navigera till medarbetarens post och markera **kassabehörigheter** och sedan redigera användarens meddelandeprenumeration.

 - Gå till sidan **funktionsprofil** (**butik** > **kanalinställningar** > **kassainställningar** > **kassaprofiler** > **funktionsprofiler**). Uppdatera egenskapen **meddelandeintervall** för att ange intervallet i minuter som meddelanden ska hämtas. Vi rekommenderar att du anger värdet till 10 minuter för att undvika onödig kommunikation till huvudkontoret. Om du anger meddelandeintervallet till ”0” inaktiveras meddelanden.  

 - Gå till **Butik** > **Butiks-IT** > **Distributionsschema**. Välj schemalägg ”1060 medarbetarna” för att synkronisera inställningar av meddelandeabonnemang och klicka sedan på **kör nu**. Synkronisera sedan behörighetsintervallet genom att välja ”1070 kanalkonfiguration” och välj sedan **kör nu**. 

## <a name="view-notifications-in-pos"></a>Visa meddelanden i kassan

När stegen är slutförda kan medarbetarna som meddelanden ställs in för se meddelandena i kassan. För att visa meddelanden, klicka på meddelandeikonen i kassans namnlist. Detta visar ett meddelandecenter med meddelanden för utförandet av orderuppfyllelse. Meddelancecentret ska visa följande grupper inom utförandet av orderuppfyllelse: 

- **Väntande order** Den här gruppen visar antalet order som har väntande status, som t.ex. order som måste godkännas av en kassaarbetare som har behörighet för uppfyllelse i butik. Om du klickar på numret på gruppen öppnas sidan **orderuppfyllande**, filtrerad för att endast visa de väntande order som tilldelats butiken för uppfyllelse. Om order accepteras automatiskt för butiken, ska antalet för den här gruppen vara noll.

- **Upphämtning i butik** Den här gruppen visar antalet order som har leveransläget **upphämtning** och upphämtning kommer från den aktuella butiken. Om du klickar på numret på gruppen öppnas sidan **orderuppfyllande**, filtrerad för att endast visa de aktiva order som är inställda på att hämtas från den aktuella butiken.

- **Leverera från butik** Den här gruppen visar antalet order som har leveransläget **Leverans** och leverans är planerad från den aktuella butiken. Om du klickar på numret på gruppen öppnas sidan **orderuppfyllande**, filtrerad för att endast visa de aktiva order som är inställda på att levereras från den aktuella butiken.

När nya order tilldelats butiken för uppfyllelse kommer meddelandeikonen att ändras för att indikera nya meddelanden och antalet för motsvarande grupper uppdateras. Användaren kan också klicka på uppdateringsikonen bredvid åtgärdsnamnet för att omedelbart uppdatera antal grupper. Antalet uppdateras också med fördefinierade intervall. En grupp med en ny artikel som inte ses av den aktuella arbetaren kommer att visa en explosionsikon som visar att den här gruppen har en ny artikel. Om du klickar på panelerna inne i meddelanden öppnas den särskilda åtgärden som det meddelandet är konfigurerat för. I de ovan nämnda scenarierna om du klickar på meddelanden öppnas sidan **orderuppfyllande** och skickar lämpliga parametrar: väntande order, butiksupphämtning och levereras från butik. 

> [!NOTE]
> Meddelanden om väntande order aktiveras i en kommande uppdatering för Dynamics 365 for Retail. 


