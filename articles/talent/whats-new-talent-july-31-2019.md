---
title: Nyheter och ändringar i Dynamics 365 for Talent (31 juli 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 7/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1fffe1bd8739723294c027c174d5e959c1c6010a
ms.sourcegitcommit: 4ff8c2c2f3705d8045df66f2c4393253e05b49ed
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2019
ms.locfileid: "1864589"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-july-30-2019"></a>Nyheter och ändringar i Dynamics 365 for Talent (30 juli 2019)

[!include [banner](includes/banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard
Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR
Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2409.


### <a name="region-support-for-canada-and-southeast-asia"></a>Regionsstöd för Kanada och Sydostasien

Vi är glada att kunna tillkännage att regionerna Kanada och Sydostasien kommer att vara tillgängliga för Microsoft Dynamics 365 for Talent den 1 augusti 2019. Med den här ändringen kan du skapa miljöer i de kanadensiska och asiatiska regionerna, och all Talent-data kommer att enbart behållas inom dessa platser. Du kan skapa en miljö i dessa nya regioner genom att markera platsen i dialogrutan Ny miljö och använda den miljön för att konfigurera Talent i LCS enligt beskrivningen i [Konfigurera Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

Datamigrering av befintliga projekt från andra områden till kanadensiska och asiatiska regioner stöds inte. Endast nya projekt kan etableras för de nya regioner som stöds.

### <a name="new-active-positions-list-page"></a>Listsida för nya aktiva befattningar

Alternativen för befattningsbaserade listor omfattar nu: **Alla befattningar**, **Aktiva befattningar**, **Öppna befattningar** och **Inaktiva befattningar**. På nya listsidan **nya aktiva befattningar** visas bara de positioner, öppna eller ifyllda, som är aktiva vid det aktuella datumet. 

### <a name="allow-course-participants-to-be-added-to-open-courses"></a>Tillåt kursdeltagare att läggas till i öppna kurser

Ändringar denna vecka löser problemet att endast direktrapporter kan registreras för öppna kurser.

### <a name="fte-analysis-displaying-incorrect-fte-number"></a>FTE-analys visar felaktigt FTE-nummer

**FTE-analys** har korrigerats på fliken **Analys** i **Personalhantering**.

### <a name="final-comments-label-translation"></a>Översättning av etiketten slutgiltiga kommentarer

Etiketten **slutgiltiga kommentarer** översätts nu i granskningsformuläret.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Förhandsgranskningsfunktioner aktiveras endast i begränsade instanser

När du etablerar en ny instans av Talent kan du ange om instanstypen är **produktion** eller **begränsat läge**. Med instanser **Begränsat läge** kan tidig test av nya funktioner göras. Alla befintliga Talent-instanser kommer att uppdateras till instanstypen **produktion**. Om du vill uppdatera en av dina befintliga förekomster till instanstypen **Begränsat läge** kontaktar du [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) för att initiera ändringsbegäran.

Mer information om hur du ändringar publiceras finns i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Visa utökad information för prestandan i Självbetjäning för chefer

Med ett nytt alternativ kan cheferna visa prestandan för både deras direktrapporter och de utökade rapporterna. För närvarande kan linjechefer tilldela och uppdatera resultatmål och utfärda nya recensioner. Dessutom kan direktchefer och deras medarbetare underhålla och uppdatera prestandajournaler för att säkerställa att processen för resultatöversynen går smidigt. När den här ändringen har implementerats kan chefer visa och underhålla prestandarelaterad information för sina utökade rapporter utöver deras underställda.
