--- 
title: "Ändra ägarskapet för försändelselagret baserat på produktionsbegäran"
description: "I den här proceduren visas hur du ändrar ägaren till försändelselagret, från leverantören till din juridiska person, om det finns en efterfrågan på lagret i produktionen."
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5925f5423d596adc4326dfff4734de2afd80b5a8
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a>Ändra ägarskapet för försändelselagret baserat på produktionsbegäran

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du ändrar ägaren till försändelselagret, från leverantören till din juridiska person, om det finns en efterfrågan på lagret i produktionen. Den här ändringen i ägarskap görs genom att skapa och bokföra en ändringsjournal för lagerägarskap. Ändringsjournalraderna för ägarskap kan skapas manuellt eller, som visas i denna registrering, baseras på befintliga produktionsbegäran. Vanligtvis utför en produktionslagerarbetsledare denna uppgift. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Om du använder dina egna data, kontrollera då att du har följande förutsättningar: ett journalnamn för lager som har skapats för lageräganderättsändring, fysiskt registrerade leverantörsägda behållningsartiklar, samt en eller flera produktionsorderrader för materialet. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.


## <a name="create-an-inventory-ownership-journal"></a>Skapa en journal över lagerägarskap
1. Gå till Lagerhantering > Journalposter > Artiklar > Lagerägarskapsändring.
2. Klicka på Ny.
    * Ändringsjournalen för lageräganderätt används för att byta ägaren till försändelselager från leverantören till nuvarande juridisk person. Denna ändring i ägarskap görs genom att frisläppa det behållningslager som ägs av leverantören och seden ta emot det lagret i nuvarande juridisk person.  
3. Ange eller välj ett värde i fältet Namn.
    * Du kan bara välja lagerjournalnamn som har en journal av typen Ownership change (ägarskapsändring).  
4. Klicka på OK.
5. Klicka på Funktioner.
6. Klicka på Create journal lines from production orders.
    * Du kan starta en ändring av ägarskapsprocessen genom att skicka en fråga till samtliga produktionslinor med krav på förbrukning av råmaterial.  
7. Välj ett alternativ i fältet Inventory issue statuses to include.
    * Detta alternativ låter dig filtrera efter utleveransstatusen för lagertransaktionerna. Du kan till exempel skapa journalrader för lager som har fysisk status Picked eller Reserved.  
8. Expandera avsnittet Poster som ska ingå.
    * I det här avsnittet kan du använda ytterligare filtrering. Du kan till exempel välja ett specifikt råmaterialdatum.  
9. Klicka på OK.

## <a name="post-the-inventory-ownership-change-journal"></a>Bokför journalen över lagerägarskapsändringar
1. Klicka på Bokför.
    * När journalen bokförs frisläpps det leverantörsägda lagret genom att använda referensen ”Ownership change". Lagret tas sedan emot som behållning genom att använda en lagertransaktion som uppdateras med en produktinleverans för inköpsorder. Observera att endast transaktioner kopplade till den bokförda journalen skapas. Inga förväntade lagertransaktioner skapas.  
2. Klicka på OK.
3. Stäng sidan.


