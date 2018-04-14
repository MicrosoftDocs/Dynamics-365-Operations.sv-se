--- 
title: "Skapa inköpspolicyer"
description: "I den här proceduren visas hur du skapar inköpspolicyer att justera med dina affärsprocesser för inköp."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b3a66443394f5bfbe51b6685513281025d68fd
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-purchasing-policies"></a>Skapa inköpspolicyer

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar inköpspolicyer att justera med dina affärsprocesser för inköp. Innan du kan skapa inköpspolicyer måste du ställa in inköpspolicyparametrarna. Det är möjligt att skapa, ändra och att överge en inköpspolicy, men du kan inte ta bort en inköpspolicy. Denna procedur utförs vanligtvis av en inköpschef. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.


## <a name="set-up-policy-parameters"></a>Ställ in policyparametrar
1. Gå till Inköpspolicyer.
2. Klicka på Parametrar.
    * Policyprioritetsregler gäller för olika nivåer i din organisation. Organisationsenheterna som visas beror på din organisationshierarki och på vilka nivåer i hierarkin som har tilldelats syftet med Intern anskaffningskontroll. Till exempel kan din organisation ha juridiska personer, kostnadsställen, regioner och avdelningar, men det kan hända att bara några av dessa har ett hierarkiskt syfte av Intern anskaffningskontroll. Som standard är organisationen av typen Företaget tillgänglig.  
3. Klicka på fliken Parametrar för policyregeltyp.
4. I trädet väljer du ”Inköpspolicy\Kontrollregel för inköpsrekvisition”.
    * Du definierar prioritetsordningen för policylösning på policynivå. Men för vissa policytyper kan du åsidosätta prioritetsordningen för enskilda policyregeltyper. Till exempel kan du definiera prioritet för inköpspolicyer i denna ordning till: kostnadsställe, avdelning, företag. Men du kanske vill att prioritetsordningen för katalogpolicyregeln ska användas i denna ordning: avdelning, kostnadsställe, företag. Då ändrar du prioritetsordningen för katalogpolicyregeln. När en anställd skapar en rekvisition, bestäms katalogen som visas av de policyer som associeras med arbetarens avdelning, sedan deras kostnadsställe och sedan deras företag.  
    * Om det finns fler än en angiven organisationsnivå, kan du använda de UPP/NED-pilarna för att ange prioritetsordningen för Kontrollregeln för inköpsrekvisition.  
5. Stäng sidan.

## <a name="create-a-new-policy"></a>Skapa en ny policy
1. Klicka på Ny.
2. Skriv ett värde i fältet Namn.
3. Ange ett värde i fältet Beskrivning.
    * En enskild inköpspolicy kan gälla för endast en organisationshierarki. Du kanske till exempel har en geografisk hierarki med namnet "Geografisk" och en kallad "Avdelning" och ha olika inköpspolicyer för varje.  
    * Välj en organisation som policyn ska gälla för.  
4. Klicka på pilen för att lägga till den valda organisationen.
    * Du kan köra den här processen om du vill lägga till fler organisationer.  

## <a name="add-a-policy-rule"></a>Lägg till en policyregel
1. I listan Policyregeltyp väljer du Rekvisitionssyftesregel.
    * Du skapar en regel som anger standardinställningrekvisitionsyftet till Förbrukning men låter istället återanskaffningtypen markeras.  
2. Klicka på Skapa policyregel.
3. Välj Ja i fältet Tillåt manuell åsidosättning.
4. Klicka på Stäng.
    * Nu kan du ställa in andra policyregler för inköpspolicyn.   Observera att en policyregeltyp inte kan ha överlappande regler som är aktiva samtidigt inom en enskild anskaffningpolicy.  
5. Stäng sidan.
6. Stäng sidan.


