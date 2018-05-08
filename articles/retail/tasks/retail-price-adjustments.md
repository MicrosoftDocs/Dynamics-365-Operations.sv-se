--- 
title: " Underhåll butiksprisjusteringar"
description: "Den här proceduren går igenom hur du skapar en butiksprisjustering."
author: josaw1
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: edfb9a1515f0af7d3272ea3fbb362bd0e6b0f129
ms.contentlocale: sv-se
ms.lasthandoff: 02/07/2018

---
# <a name="retail-price-adjustments"></a> Underhåll butiksprisjusteringar

[!include [task guide banner](../includes/task-guide-banner.md)]

Den här proceduren går igenom hur du skapar en butiksprisjustering. En butiksprisjustering kan ange en artikels försäljningspris direkt eller ändra dess basförsäljningspris eller handelsavtalsförsäljningspris. I proceduren används demonstrationsföretaget USRT.

1. Klicka på prissättning och rabatter.
2. Klicka på fliken Prisjusteringar.
3. Klicka på Ny.
    * Härifrån kan du skapa alla de flesta vanliga regler för prissättning och rabatter, inklusive butiksrabatter, prisjusteringar, handelsavtalsjournaler och kategoriprissättningsregler.  
4. Klicka på Prisjustering.
5. Skriv ett värde i fältet Namn.
6. Expandera avsnittet Rader.
7. Klicka på Lägg till.
    * Ange 81126 i fältet Produkt i det här exemplet.    Ange sedan värdet 10,0 i fältet Rabattprocent.  
    * En prisjustering för typ av rabattprocent minskar ett basförsäljningspris eller handelsavtalsförsäljningspris.  
8. Klicka på Lägg till.
    * Ange 81125 i fältet Produkt i det här exemplet.    Välj sedan Kassarabattbelopp i fältet Rabattmetod.    Ange slutligen 5,0 i fältet Kassarabattbelopp.  
    * En rabattyp för kassarabatt i beloppsform är ett belopp som dras av från ett baspris eller ett handelsavtalspris.  
9. Klicka på prisgrupper.
    * Välj RP-Houston i fältet Prisgrupp.  
    * Det kopplar prisjusteringen till Houston-butiken.  
10. Klicka på Spara.
11. Stäng sidan.
12. Välj Aktiverad i fältet Status.
13. Klicka på Spara.
14. Stäng sidan.
15. Uppdatera sidan.


