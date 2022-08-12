---
title: Nyheter och ändringar i Dynamics 365 Human Resources 5 oktober 2021
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources för 5 oktober 2021.
author: marcelbf
ms.date: 10/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba24afd16a471abb36a6f7bc9a8610acec374190
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067984"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-5-2021"></a>Nyheter och ändringar i Dynamics 365 Human Resources 5 oktober 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här artikeln beskriver funktioner som är nya, ändrade eller kommer snart i Microsoft Dynamics 365 Human Resources.

Mer information om uppdateringsprocessen och schema finns i [uppdateringsprocessen](hr-admin-setup-update-process.md).

Mer information om nya funktioner och deras förväntade allmänna tillgänglighetsdatum finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>I den här versionen

I den här versionen ingår följande nya funktioner och felkorrigeringar. Ändringarna tillämpas på versionsnummer 8.1.4485.

### <a name="new-features"></a>Nya funktioner

Följande funktioner är i allmänhet tillgänglig i den här versionen.

| Funktion | Utgivningsplan | Dokumentation |
|---|---|---|
| Plattformsuppdatering 10.0.21 (45) | -- | [Plattformsuppdateringar för version 10.0.21 av appar för ekonomi och drift (oktober 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21) |


### <a name="bug-fixes"></a>Felkorrigeringar

Den här versionen innehåller följande felkorrigeringar.

> [!NOTE]
> Vårt mål är att få den här informationen så snart som möjligt. Vi kan komma att uppdatera detta ämne i syfte att inkludera felkorrigeringar som kommit med i versionen efter det att ämnet publicerades första gången.

| Utfärda nummer | Problem | Beskrivning |
|---|---|---|
| 598896 | Medarbetarbeloppet visas inte förrän medarbetaren har slutfört registreringen | På sidan **Självbetjäning för medarbetare** visas inte medarbetarbeloppet för förmånen. Medarbetarbeloppet visas nu på sidan **Självbetjäning av förmåner**.  |
| 613440 | Det gick inte att exportera data från **Datahanteringen** | När du exporterar data för ett projekt i **Datahantering** misslyckas exporten oväntat. |
| 618327 | Stängda och framtida perioder visas på sidan **Rapportparametrar** för förmånsutdraget | När du navigerar till **förmånsutdrag** in **Självbetjäning för medarbetare** visar sidan **Rapportparametrar** snabbflikarna **Poster som ska inkluderas** och **Kör i bakgrunden**. Dessa avsnitt har tagits bort.|
| 618326 | En felaktig **Rapportparametrar**-sida visas i **Självbetjäning för medarbetare** för förmånsutdraget| När denne navigerade till målsidan **Rapport för förmånsutdrag** kunde användaren välja förmånsplanperioder som är stängda eller framtidsdaterade, vilket leder till en tom sida. Endast den aktuella förmånsplansperioden ska visas i listan. |

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
|Fel när en rapport e-postas med **GER-rapportdestination** | Förmånsutdraget kan ställas in att använda e-postparametrar på sidan **GER-rapportdestinationer**. När användaren slutför inställningarna och skriver ut rapporten får han eller hon ett formateringsfel, och förmånsmeddelandet skickas inte.|

## <a name="feature-management-changes"></a>Ändringar i funktionshantering

| Funktion | Beskrivning |
|---|---|
|Vy över utökade rapporter för prestationsjournaler | Denna funktion aktiveras som standard i denna version. |

## <a name="coming-soon"></a>Kommer snart

En fullständig lista över planerade funktioner och deras schemalagda versioner finns i [Översikt över Dynamics 365 Human Resources 2021 utgivningscykel 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funktion | Detaljer |
|---|---|
| Plattformsuppdatering 10.0.22 (46) | Lansering av plattformsuppdatering 10.0.22 planeras i och med nästa serviceversion den 1 november 2021. Mer information finns i [Plattformsuppdateringar för version 10.0.22 av appar för ekonomi och drift (november 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22). |



## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2021 utgivningsvåg 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

