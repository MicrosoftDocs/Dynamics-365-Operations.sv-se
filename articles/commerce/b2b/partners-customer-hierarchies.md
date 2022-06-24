---
title: Hantera B2B-affärspartners med hjälp av kundhierarkier
description: Denna artikel beskriver hur man använder kundhierarkier för att hantera affärspartners för Microsoft Dynamics 365 Commerce på B2B-näthandelssajter.
author: josaw1
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ddd02045b5df3ce20160a4feaa23339475823d3d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864991"
---
# <a name="manage-b2b-business-partners-using-customer-hierarchies"></a>Hantera B2B-affärspartners med hjälp av kundhierarkier

[!include [banner](../../includes/banner.md)]

Denna artikel beskriver hur man använder kundhierarkier för att hantera affärspartners för Microsoft Dynamics 365 Commerce på B2B-näthandelssajter.

I Commerce headquarters används en entitet för *kundhierarki* som representerar affärspartners organisationerna som ska använda din näthandelsplats för B2B. Innan du kan börja använda kundhierarkier för att hantera affärspartners måste du aktivera B2B-näthandelsfunktionerna i Commerce headquarters och sedan definiera en nummerserie för kundhierarkin.

## <a name="enable-the-b2b-e-commerce-feature-in-commerce-headquarters"></a>Aktivera funktionen för B2B-näthandel i Commerce headquarters

Om du vill använda funktionerna för B2B-näthandel måste du först aktivera funktionen för **Aktivera användning av B2B-funktioner för näthandel** i Commerce headquarters.

1. Gå till **Arbetsytor \> Funktionshantering**.
1. På fliken **Alla**, använd filterrutan för att söka efter **Modul: Butik och handel**.
1. Hitta funktionen **Aktivera användning av B2B-funktioner för näthandel** och välj sedan **Aktivera nu** i nedre vänstra hörnet.

## <a name="define-a-number-sequence-for-the-customer-hierarchy"></a>Definiera en nummerserie för kundhierarkin

Nummerserier används för att generera läsliga unika identifierare för huvuddataposter och transaktionsposter och som kräver identifierare. Du måste definiera en nummerserie som ska användas för att generera ID för kundhierarkin. Mer information om nummerserier, se [Översikt över nummerserier](/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview).

För att definiera en nummersekvens för kundhierarkin i Commerce headquarters med dessa steg.

1. Gå till **Butik och handel \> Administrationsinställningar \> Nummerserier \> Nummerserier**.
1. Skapa en ny nummerserie eller välj en befintlig nummerserie om du vill återanvända den.
1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> delade Commerce-parametrar**.
1. På fliken **Nummerserier** lägger du till den nummerserie du skapat eller valt tidigare till referensen för **kundhierarki-ID:t**.

![Nummerserien som läggs till kundhierarkins ID-referens.](../media/NumberSequenceCustHierarchy.png)

## <a name="how-the-approval-process-works"></a>Hur godkännandeprocessen fungerar

När en affärspartner begär att få gå med i en B2B-näthandelsplats sparar systemet begäran som en *potentiell kund*. En person på Commerce headquarters, till exempel en verksamhetschef för detaljhandeln, kan godkänna eller avvisa partnerförfrågningar. För mer information om hur du hanterar förfrågningar från affärspartner och godkännanden av potentiella kunder, se [Hantera affärspartners på B2B näthandelswebbplatser](manage-b2b-users.md).

När en potentiell kund godkänns skapas två nya kundposter i systemet:

- En kundpost av typen **organisation** representerar den organisation som begär att bli affärspartner.
- En kundpost i typen **person** representerar personen som skickade förfrågan.

Dessutom skapas en ny kundhierarkipost i kundhierarkierna i **Butik och handel \> Kunder \> Kundhierarkier**. Den här kundhierarkin har följande egenskaper:

- **Kundhierarki-ID** – Ett unikt ID för kundhierarkin. Detta ID använder den nummerserie som definierats i delade Commerce-parametrar.
- **Namn** – Organisationsnamnet för affärspartnern, enligt vad som angetts i begäran om registrering. Detta fält kan redigeras.
- **Syfte** – Denna egenskap är inställd på det fördefinierade värdet **B2B-organisation**.
- **Organisation** – Kund-ID för affärspartnerns organisation.

Personen som skickade den inmatade begäran läggs till på snabbflikarna **Hierarki** och rollen **Admin** tilldelas honom eller hon. När administratören lägger till fler användare till partnerorganisationen på en B2B-webbplats skapas en ny kundpost för respektive användare. Denna kundpost läggs också till i den relevanta kundhierarkiposten för affärspartnern och har rollen **användare** tilldelad.

### <a name="examples"></a>Exempel

En person som heter Sam J. skickar en egen begäran på uppdrag av Microsoft-organisationen. När begäran har godkänts skapas två nya kundkonton: en av typen **person** för Sam J och en av typen **organisation** för Microsoft.

Som exemplet i följande illustration visar skapas också en ny kundhierarkipost. Den här posten har samma namn som organisationen (**Microsoft**) och rollen **Admin** tilldelas Sam J. som administratör lägger Sam J. till alla andra Microsoft-användare av B2B-webbplatsen i den här hierarkin och tilldelar **användaren** till dem. I det här exemplet har Sush R. lagts till som användare.

![Exempel på en kundhierarkipost.](../media/CustomerHierarchy2.png)

Öppna kundposten om du vill ta reda på om en kund är associerad med en kundhierarki. I följande bild visas fältet **Kundhierarki-ID** i avsnittet **B2B** på snabbfliken **Butik** och visar om kunden ingår i en kundhierarki, och alternativet **B2B-administratör** anger om kunden är administratör för hierarkin.

![Exempel på B2B-avsnittet på snabbfliken Butik för en kundpost, där kunden associeras med en hierarki och anges som administratör.](../media/CustomerHierarchyMapping2.png)

I de flesta fall ska egenskapsvärden för alla kundposter i en hierarki matcha. Eftersom alla affärspartnersanvändare exempelvis ska få liknande priser för produkter, ska deras prisgrupp och associerade konfigurationer matcha. Systemet framtvingar dock inte denna överensstämmelse. Därför ansvarar relevanta Commerce headquarterssanvändare för att egenskapsvärden och konfigurationer ska matcha för alla kunder i en given hierarki.

Användare av Commerce headquarters kan även söka efter egenskapsvärden för alla kundposter i hierarkin i en vy sida vid sida. Som exemplet i följande illustration visar kan du använda alternativet **Allmänt** i listrutan på snabbflikarna **Hierarki** och sedan välja vilket avsnitt som helst i kundposten för att visa relaterade egenskaper. Användare kan redigera egenskapsvärdena direkt i den här vyn. Om du vill kopiera alla värden från en administratörskundpost till alla användare väljer du **Åsidosätt** på snabbfliken **Hierarki**.

![Exempel på en kundhierarkipost där knappen Åsidosätt och alternativet visas i listrutan.](../media/HierarchyDetails2.png)

[!include [footer-include](../../includes/footer-banner.md)]
