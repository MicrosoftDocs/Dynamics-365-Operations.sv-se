---
title: "Nyheter och ändringar i Dynamics 365 for Talent Core HR (31 oktober 2018)"
description: "Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 10/31/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c5acd09e25ecd5fefa637342f83d0ee0f1891402
ms.contentlocale: sv-se
ms.lasthandoff: 11/01/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-31-2018"></a>Nyheter och ändringar i Dynamics 365 for Talent Core HR (31 oktober 2018)

[!include [banner](includes/banner.md)]

**Skapa 8.1.2031**

Det här ämnet beskriver nya eller ändrade funktioner i Core HR.

## <a name="create-links-from-talent-to-finance-and-operations"></a>Skapa länkar från Talent till Finance and Operations
Detta navigeringsfält låter dig koppla från Talent till Finance and Operations vilket ger dig direkt navigering till Finance and Operations-sidor. När länkar är konfigurerade kan du kan ange namn och grupp för länken där länken ska visas i Talent och målsidan ska öppnas inne i Finance and Operations.

#### <a name="coming-soon"></a>Kommer snart
Fältsammanhang läggs till i framtiden för att tillåta direkt navigering till motsvarande poster i Finance and Operations. Du kan till exempel använda **Länk till fältet** för att ge kontext till att navigera direkt till en viss medarbetare eller position i Finance and Operations.

### <a name="configure-target-systems"></a>Konfigurera målsystem

I Talent kan systemadministratörer definiera länkar som ska exponeras genom Arbetsyta för systemadministration. En del av konfigurationen är de Finance and Operations-miljöer du vill navigera till som ”mål” för länken. Du kan göra detta genom att ge målsystemet ett namn och URL-adressen till Finance and Operations-miljön. Här är ett exempel på en Finance and Operations-URL som du skulle tillhandahålla: https://devax00124aos.cloud.test.dynamics.com/. När du har konfigurerat dina målsystem kan du definiera dina länkar.

### <a name="configure-links"></a>Konfigurera länkar

Varje länk som skapats måste ha följande information definierad.

- Länk - namnet på den länk som endast används för identifiering.

- Aktivera den här länken - ställ in på **Ja** om du vill visa länken för användare av Talent.

- Visningsnamn – definiera namnet som ska visas som en länk till Finance and Operations. Informationen har för närvarande inte översatts.

- Ytlänk på formulär - Välj vilken sida du vill visa länken på.

- Grupp - grupper är inte obligatoriska, men om du vill organisera länkarna med hjälp av grupper väljer du en befintlig grupp eller skapar en ny en med hjälp av fältet **grupp**.

- Målsystem - Välj vilket målsystem som skapades med alternativet **konfigurera målsystem**. Detta är Finance and Operations-miljön som kommer att användas vid navigering med hjälp av länken.

- Använd användarens nuvarande företag, välj **Ja** om du vill använda användarens nuvarande företag när du navigerar till Finance and Operations. Om **Nej** är markerat kan du välja det företag som ska användas.

- Målmenyalternativ - ange menyalternativet från Finance and Operation som länken ska användas för att navigera. Menyalternativ som du kan navigera direkt till är tillgängliga. För att hitta det menyalternativ som krävs, öppna Finance and Operations och öppna den sida som är målet för navigeringen. Kopiera menyalternativet från URL:en. Om du till exempel vill att länken ska ta dig till medarbetarlistan i Finance and Operations anger du värdet som visas efter den ”&mi” i URL-adressen. https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees. Menyalternativet för att navigera till listsidan för medarbetare i det här exemplet är: HcmWorkerListPage_Employees.

- Länk till datakälla – Välj den källa för data som länken refererar till. De vanligaste datakällorna såsom **arbetare** och **befattning** är tillgängliga.

- Länk till fält - (kommer snart) detta fältval tillåter direkt navigering från en enskild post i Talent till en enskild post i Finance and Operations.

### <a name="access-to-links"></a>Tillgång till länkar

Systemadministratörer vill se de nyligen skapta länkarna på de definierade sidorna även om alternativet **aktivera den här länken** är inställt på **Nej**. Detta kan användas för att testa länkar innan du visar dem för andra medarbetare. Andra roller visar endast de konfigurerade länkarna när alternativet **aktivera den här länken** är inställd på **Ja**. Medarbetare som har åtkomst till de sidor där länkarna exponeras kommer att ha åtkomst till länken.

Användare kan även ha säkerhetsbehörighet inom Finance and Operations definierade för att komma åt sidor i Finance and Operations. Om inte visas en dialogruta för säkerhet när du använder länken.


## <a name="other-changesfixes"></a>Andra ändringar/korrigeringar

### <a name="positions-with-a-future-start-date-cannot-be-assigned-to-a-new-employee"></a>Befattningar med ett startdatum i framtiden kan inte tilldelas en nyanställd

Ändringar har gjorts för att tillåta medarbetarnas tilldelningar till framtida befattningar. Befattningar vars startdatum i framtiden kan väljas och medarbetares tilldelning görs när arbetsflödet sparas eller slutförs (om arbetsflödet är aktiverat).

### <a name="new-employee-cannot-be-assigned-existing-position"></a>Nya medarbetare kan inte tilldelas befintlig befattning

Ändringar har gjorts så att nya medarbetares tilldelningen nu kan tilldelas befintliga positioner.

### <a name="seniority-dateoffice-location-disappears-when-the-employment-start-date-is-in-the-past-and-the-record-is-saved"></a>Datum för tjänsteålder/kontorsadress försvinner när anställningens startdatum redan inträffat och posten sparas

Ändringar som har gjorts för att korrigera visningen av **Datum för tjänsteålder** och **Kontorsadress** när du sparar ändringar för tidigare anställda.

### <a name="cant-enter-data-for-future-dated-employments-on-the-worker-page"></a>Det går inte att ange data för framtida anställningar på sidan för medarbetare

Anställningsuppgifter för framtida anställningar har inaktiverats på huvudsidan för medarbetare. Anställningsuppgifter kan anges via sidorna **Datumhanterare**. Ytterligare ändringar kommer göras i framtida versioner för att tillåta inmatning av anställningsuppgifter direkt under arbetsflödesprocessen.

### <a name="add-validfrom-and-validto-to-hcmpersonalcontactpersonentity"></a>Lägg till ValidFrom och ValidTo i HcmPersonalContactPersonEntity

Entiteten Data Management Framework (DMF) HcmPersonalContactPersonEntity har uppdaterats att inkludera datum för ”giltig från” och ”giltig till” för att tillåta vissa scenarier för förmånsintegration. 

## <a name="known-issue"></a>Kända problem
- **Problem**: när du lägger till en ny bilaga till en arbetare blir knapparna **Ny** och **Redigera** nedtonade. 
- **Lösning:** innan du öppnar bilagesidan, kontrollera att faktaboxar på sidan **Arbetare** är stängda. Om faktarutorna är stängda när sidan **arbetare** hämtas kommer knapparna för bifogade filer att aktiveras. (Det här problemet kommer att åtgärdas i nästa plattformsuppdatering.)

