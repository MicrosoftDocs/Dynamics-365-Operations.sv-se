---
title: Skapa inköpspolicyer
description: I denna artikel visas hur du skapar inköpspolicyer att justeras med dina affärsprocesser för inköp.
author: GalynaFedorova
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicyParameters, SysPolicy, RequisitionPurposeRule
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a8d42eaf22730f572e2733dec4318e5e4603d74
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2022
ms.locfileid: "9732715"
---
# <a name="create-purchasing-policies"></a>Skapa inköpspolicyer

[!include [banner](../../includes/banner.md)]

I denna artikel visas hur du skapar inköpspolicyer att justeras med dina affärsprocesser för inköp. Innan du kan skapa inköpspolicyer måste du konfigurera inköpspolicyparametrarna. Det är möjligt att skapa, ändra och att överge en inköpspolicy, men du kan inte ta bort en inköpspolicy. Denna procedur utförs vanligtvis av en inköpschef. Du kan använda den här proceduren i demonstrationsföretaget USMF eller på dina egna data.


## <a name="set-up-policy-parameters"></a>Ställ in policyparametrar
1. I navigeringsfönstret går du till **moduler > anskaffning och källa > inställningar > principer > inköpspolicyer**.
2. Klicka på **Parametrar** i åtgärdsfönstret.
    - Policyprioritetsregler gäller för olika nivåer i din organisation. Organisationsenheterna som visas beror på din organisationshierarki och på vilka nivåer i hierarkin som har tilldelats syftet med Intern anskaffningskontroll. Till exempel kan din organisation ha juridiska personer, kostnadsställen, regioner och avdelningar, men det kan hända att bara några av dessa har ett hierarkiskt syfte av Intern anskaffningskontroll. Som standard är organisationen av typen Företaget tillgänglig.  
3. Välj fliken **Parametrar för policyregeltyp**.
4. I trädet går du till **Inköpspolicy > Kontrollregel för inköpsrekvisition**.
    - Du definierar prioritetsordningen för policylösning på policynivå. Men för vissa policytyper kan du åsidosätta prioritetsordningen för enskilda policyregeltyper. Till exempel kan du definiera prioritet för inköpspolicyer i denna ordning till: kostnadsställe, avdelning, företag. Men du kanske vill att prioritetsordningen för katalogpolicyregeln ska användas i denna ordning: avdelning, kostnadsställe, företag. Då ändrar du prioritetsordningen för katalogpolicyregeln. När en anställd skapar en rekvisition, bestäms katalogen som visas av de policyer som associeras med arbetarens avdelning, sedan deras kostnadsställe och sedan deras företag.  
    - Om det finns fler än en angiven organisationsnivå, kan du använda de UPP/NED-pilarna för att ange prioritetsordningen för Kontrollregeln för inköpsrekvisition.  
5. Stäng sidan.

## <a name="create-a-new-policy"></a>Skapa en ny policy
1. Välj **Ny**.
2. Skriv ett värde i fältet **Namn**.
3. I fältet **Beskrivning** anger du ett värde.
    - En enskild inköpspolicy kan gälla för endast en organisationshierarki. Du kanske till exempel har en geografisk hierarki med namnet "Geografisk" och en kallad "Avdelning" och ha olika inköpspolicyer för varje.  
    - Välj en organisation som policyn ska gälla för.  
4. Välj på pilen för att lägga till den valda organisationen.
    - Du kan köra den här processen om du vill lägga till fler organisationer.  

## <a name="add-a-policy-rule"></a>Lägg till en policyregel
1. I listan **Policyregeltyp** väljer du **Rekvisitionssyftesregel**.
    - Du skapar en regel som anger standardinställningrekvisitionsyftet till Förbrukning men låter istället återanskaffningtypen markeras.  
2. Välj **Skapa policyregel**.
3. Välj **Ja** i fältet **Tillåt manuell åsidosättning**.
4. Välj **Nära**.
    - Nu kan du konfigurera andra policyregler för inköpspolicyn. Observera att en policyregeltyp inte kan ha överlappande regler som är aktiva samtidigt inom en enskild anskaffningpolicy.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
