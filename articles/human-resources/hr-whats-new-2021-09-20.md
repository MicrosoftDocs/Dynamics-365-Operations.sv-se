---
title: Nyheter och ändringar i Dynamics 365 Human Resources 20 september 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 20 september 2021.
author: marcelbf
ms.date: 09/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3f4fc4768f8c96678b216709f78af6d3ddfd4132
ms.sourcegitcommit: ba8ca42e43e1a5251cbbd6ddb292566164d735dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/25/2021
ms.locfileid: "7556943"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-20-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 20 september 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver nya, ändrade och kommande funktioner i Microsoft Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4464.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
|---|---|---|
| Aktivera förenklad löneintegrering (löneintegrerings-API:er) | [Aktivera förenklad integrering löneleverantörer](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Löneintegration-API](hr-admin-integration-payroll-api-introduction.md) |
| Tillåta att medarbetare markeras som klara att betalas | [Tillåta att medarbetare markeras som klara att betalas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Klar att betalas](/dynamics365/human-resources/hr-compensation-payroll) |

### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan komma att uppdatera detta ämne i syfte att inkludera felkorrigeringar som kommit med i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem | Beskrivning |
|---|---|---|
| 619774 | Att redigera adressbeskrivning synkroniseras inte till Dataverse i realtid. | När du redigerar beskrivningen av en arbetsadress synkroniseras inte den uppdaterade beskrivningen i realtid till Dataverse. Abonnemanget i registret **Logistikplats** uppdaterades för att skicka en uppdatering. |
| 614603| Fel på sidan **Arbetare** när parametern **Arbetares personalåtgärder** inte har valts. | När du anställer en ny **arbetare** eller navigerar till arbetarsidan visas följande fel, "Fält **åtgärdstyp för personal måste fyllas i**", även om **personalåtgärder** är inaktiverade. |
| 615367 | En varning visas på fliken **Godkänd ledighet** och om den visas på fel sätt. | Om tjänstledighetsenheten är inställd på **Dagar** innan funktionen **Konfigurera ledighetsenheter per tjänstledighetstyp** visas en ogiltig varning och felaktiga kolumner på fliken **Godkänd ledighet**. |


## <a name="in-preview"></a>I förhandsgranskning

Följande nya funktioner är i förhandsgranskning. Mer information om hur du aktiverar och inaktiverar funktioner finns i [Hantera funktioner](hr-admin-manage-features.md).

| Funktion | Utgivningsplan | Dokumentation |
|---|---|---|
| Arbetsyta för förmånshantering | [Arbetsyta för hantering av förmåner (förhandsversion)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Arbetsyta för förmånshantering](hr-benefits-management-workspace.md) |
| Anpassade fält i Berättigande |[Stöd för anpassade fält för bearbetning av berättigande](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Använda anpassade fält i bearbetning av berättigande](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |
| Förmånsutdrag |[Förmånsutdrag](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) | [Förmånsutdrag](hr-benefits-statement.md) |

### <a name="benefits-statement-known-issues"></a>Kända problem med förmånsutdrag

| Problem | Beskrivning |
|---|---|
| Sidan **Rapportparametrar** i **Självbetjäning för medarbetare** för förmånsutdrag är fel. | När du navigerar till **förmånsutdrag** in **Självbetjäning för medarbetare** visar sidan **Rapportparametrar** snabbflikarna **Poster som ska inkluderas** och **Kör i bakgrunden**.  De här måste tas bort. |
| Stängda och framtida perioder visas på sidan **Rapportparametrar** för förmånsutdraget. | När du navigerar till målsidan **Rapport för förmånsutdrag** kan användaren välja förmånsplanperioder som är stängda eller framtida daterade, vilket leder till en tom sida. Endast den aktuella förmånsplansperioden ska visas i listan. |
|Fel när rapport som använder GER-rapportens destination skickas via e-post. | Förmånsutdraget kan ställas in om du vill använda e-postparametrar på sidan **GER-rapportdestinationer**. När användaren slutför inställningarna och skriver ut rapporten får han eller hon ett formateringsfel, och förmånsmeddelandet skickas inte.|


## <a name="coming-soon"></a>Kommer snart

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funktion | Information |
|---|---|
| Plattformsuppdatering 10.0.21 (45) | Lansering av plattformsuppdatering 10.0.21 planeras i och med nästa serviceversion den 4 oktober 2021. Mer information finns i [Plattformsuppdateringar för version 10.0.21 av Finance and Operations-appar (oktober 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
|Vy över utökade rapporter för prestationsjournaler | Den här funktionen aktiveras som standard i nästa utgåva. |


## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
