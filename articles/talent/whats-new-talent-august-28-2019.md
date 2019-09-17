---
title: Nyheter och ändringar i Dynamics 365 for Talent (27 augusti 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 8/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: andreabichsel
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-08-27
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a405ee96c36dd803fb46894ab58eca9dbfd81b5f
ms.sourcegitcommit: 097492a9e4f53a5e1fd5385d8764798518326818
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2019
ms.locfileid: "1927996"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-august-27-2019"></a>Nyheter och ändringar i Dynamics 365 for Talent (27 augusti 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2447. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Förhandsgranskningsfunktioner aktiveras endast i begränsade instanser

När du etablerar en ny instans av Talent kan du ange om instanstypen är produktion eller begränsat läge. Med instanser Begränsat läge kan tidig test av nya funktioner göras. Alla befintliga Talent-instanser kommer att uppdateras till instanstypen produktion. Om du vill uppdatera en av dina befintliga förekomster till instanstypen Begränsat läge kontaktar du Support för att initiera ändringsbegäran.

Mer information om hur du ändringar publiceras finns i [Etablera Talent](./provisioning-talent.md).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Visa utökad information för prestandan i Självbetjäning för chefer

Med ett nytt alternativ kan cheferna visa prestandan för både deras direktrapporter och de utökade rapporterna. För närvarande kan linjechefer tilldela och uppdatera resultatmål och utfärda nya recensioner. Dessutom kan direktchefer och deras medarbetare underhålla och uppdatera prestandajournaler för att säkerställa att processen för resultatöversynen går smidigt. När den här ändringen har implementerats kan chefer visa och underhålla prestandarelaterad information för sina utökade rapporter utöver deras underställda.

### <a name="deleting-legal-entities-isnt-allowed-if-employees-exist-within-the-company-339849"></a>Det går inte att ta bort juridiska personer om medarbetare finns i företaget (339849)

Med den här ändringen kan du inte ta bort eller radera företag om medarbetare och andra relaterade data finns för den juridiska personen.

### <a name="compensation-management-business-intelligence-analytics-dont-match-on-the-compensation-workspace-322493"></a>Business Intelligence-analys för kompensationshantering matchar inte kompensationsarbetsytan (322493)

I den här versionen har kompensationsanalysen justerats för att exakt avspegla de planer som har tilldelats medarbetare.

### <a name="workflow-placeholder-company-displays-dat-when-hiring-employees-through-workflow-343905"></a>Platshållare för arbetsflöde %company% visar DAT vid anställning av medarbetare via arbetsflöde (343905)

Med den här versionen visar platshållare för företag den juridiska person som är kopplad till den nya medarbetarens anställning.

### <a name="the-cdsjobposition-entity-displays-an-error-when-valid-to-date-is-set-349387"></a>CDSJobPosition-enheten visar ett fel när giltigt till-datum har angetts (349387)

I den här versionen tillåter datakällorna **befattningsdetalj** och **befattningens varaktighet** i entiteten **CDSJobPosition** för redigeringar från Common Data Service till fältet **Gäller från**. 

### <a name="for-employee-termination-the-last-day-worked-is-populated-on-assignment-end-date-332496"></a>För uppsägning av en medarbetare fylls den sista arbetade dagen i Tilldelningens slutdatum (332496)

Denna ändring är nu standard för befattningen **Tilldelningens slutdatum** till **Anställningens slutdatum**. Du kan ändra dessa standardvärden när du anger data.

### <a name="legal-entities-arent-limited-with-hire-338871"></a>Juridiska personer är inte begränsade till anställning (338871)
 
Denna ändring begränsar anställningsprocessen så att endast de juridiska personer som användaren har åtkomst till visas.  

## <a name="in-preview"></a>I förhandsgranskning

### <a name="streamlined-employee-entry-and-navigation"></a>Strömlinjeformad medarbetarinmatning och navigering

Den här funktionen är nu tillgänglig i miljöer med begränsat läge och testning. Om du vill aktivera den här funktionen navigerar du till **Systemadministration > Länkar > Inställningar > Systemparametrar > Förhandsfunktioner**. Välj **Förbättrade arbetarformulär och navigering**. Dessa ändringar aktiveras för alla användare. Du kan stänga av det här alternativet när du vill.

Mer information finns i [strömlinjeformad medarbetarinmatning och navigering](./streamlined-employee-entry.md)

## <a name="coming-soon"></a>Kommer snart

### <a name="platform-update-29"></a>Plattform update 29

Ytterligare information om plattformsuppdatering 29 finns i [Förhandsgranskningsfunktioner i Dynamics 365 for Finance and Operations plattformsuppdatering 29 (oktober 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).
