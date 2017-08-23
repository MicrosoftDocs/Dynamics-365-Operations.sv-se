--- 
title: " Underhåll butiksprisjusteringar"
description: "Den här proceduren går igenom hur du skapar en butiksprisjustering."
author: josaw1
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: ab13aced30f90c4d7c8b96f30340fff6e3eee927
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="retail-price-adjustments"></a> Underhåll butiksprisjusteringar

[!include[task guide banner](../includes/task-guide-banner.md)]

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


