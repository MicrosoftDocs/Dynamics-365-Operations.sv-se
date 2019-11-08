---
title: Hjälpmedelsfunktioner
description: Det här avsnittet beskriver de funktioner som hjälper användare med olika handikapp.
author: TLeforMicrosoft
manager: AnnBe
ms.date: 09/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 7cc63320a3ba055a0c18ab59447f34a86bc0dc87
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180862"
---
# <a name="accessibility-features"></a>Hjälpmedelsfunktioner

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver de funktioner som hjälper användare med olika handikapp att använda denna app. Till exempel finns funktioner för användare som använder synhjälpmedel som skärmläsaren i Microsoft Windows.

## <a name="windows-narrator-and-keyboard-only-access"></a>Windows skärmläsare och tangentbordsexklusiv åtkomst

Alla fält och alla kontroller bär en etikett och en beskrivning av tillämpliga genvägar. En skärmläsare kan läsa etikett och beskrivning.

## <a name="shortcuts-for-the-most-frequently-performed-actions"></a>Kortkommandon för de vanligaste åtgärderna

För de flesta användare omfattar daglig systemanvändning en stor mängd data och tangentbordsinteraktion. Vi har skapat genvägar för att hjälpa dig att ”hoppa” runt på skärmen och mellan olika genvägar för särskilda åtgärder i syfte att förbättra användarupplevelsen. Mer information finns i [Kortkommandon](shortcut-keys.md).

## <a name="navigation-search"></a>Navigeringsökning

Alla sidor som nås via menyn Navigeringsfönster (menyn längst till vänster) är även tillgänglig via rutan **Sök**. Tryck på Alt+G för att flytta fokus till rutan **Sök** och ange sedan sidan namn eller beskrivning.

![”Bankkonton” som anges i Sökrutan](media/6d08b0be32808221023e2aa92d69fd70.png "\"Bank accounts\" entered in the Search box")

Mer information finns i [Navigeringssökning](navigation-search.md).

> [!NOTE]
> Du kan endast navigera till överordnade sidor. Sekundära sidor behöver tillgång till information eller kontext från sin överordnade sida.

## <a name="action-search-for-keyboard-only-users-or-for-heads-down-data-entry"></a>Åtgärdssökning för användare som endast använder tangentbord eller för direkt datainmatning

Varje åtgärd som finns på en sida kan nås från tangentbordet via fliksekvensen. Information om fliksekvensen kommer senare i det här avsnittet. Om du vill köra åtgärder mer direkt kan du använda sökfunktionen för åtgärder.

### <a name="example"></a>Exempel

Du ska köra åtgärden **Meddelandelogg för e-post** som visas i gruppen **E-postmeddelande** på fliken **Försäljningsorder** i åtgärdsfönstret.

![Meddelandeloggs-åtgärd för e-post i åtgärdsfönstret](media/f0d78399e7fafcd85ded1cd1e3d34f3c.jpg "\"Meddelandeloggs-åtgärd för e-post i åtgärdsfönstret")

Ett alternativ är att använda tangentbordet. Tryck på Ctrl+F6 för att flytta fokus till åtgärdsfönstret och tryck sedan på Tabb flera gånger för att bläddra igenom alla flikar och åtgärder tills åtgärden **Meddelandelogg för e-post** är i fokus.

Du kan emellertid också köra åtgärden mer direkt. Tryck på Ctrl + apostrof (') att visa sökrutan för åtgärder.

![Sökruta för åtgärder](media/80f7e8c5ac412fdf2c8a12f7728f135a.jpg "Sökruta för åtgärder")

I sökrutan skriver du ord som beskriver åtgärden. Åtgärden görs tillgänglig för dig och du kan köra den direkt. Genom att exempelvis skriva **e-post**, **medde** (en del av ett ord) eller **logg** kan du ”hoppa” till funktionen för meddelandelogg för e-post.

![”E-post” som anges i Sökrutan](media/image4.png "\"E-post\" som anges i Sökrutan")

![”Meddelande” som anges i Sökrutan](media/image5.png "\"Meddelande\" som anges i Sökrutan")

![”Logg” som anges i Sökrutan](media/image6.png "\"Logg\" som anges i Sökrutan")

När du är klar trycker du på Ctrl + apostrof igen för att återföra fokus till det fält som du arbetade med innan du körde åtgärdssökningen.

Mer information finns i [Åtgärdssökning](action-search.md).

## <a name="tab-sequence"></a>Tabbsekvens

Vid vardaglig systemanvändning krävs inte alla fält för att utföra vanliga uppgifter. fliksekvensen är därför "optimerad" som standard. Tabbstopp placeras endast på de fält som är viktiga för vanliga scenarier.

Du upptäcker emellertid kanske att vissa fält som du ofta använder för att utföra uppgifter som inte finns med i den förvalda fliksekvensen. Om du använder Windows skärmläsare kan du då använda tangentbordskommandon i Windows skärmläsare för att nå dessa fält och granska innehållet. Alternativt kan du aktivera alternativet **Utökad fliksekvens** på sidan **Alternativ**. Det här alternativet inkluderar samtliga redigerbara och skrivskyddade fält i fliksekvensen. Du kan sedan använda sidoanpassningen för att skapa en anpassad fliksekvens och utelämna fält som inte behöver ingå i fliksekvensen. Mer information om anpassning finns i [Anpassa användarupplevelsen](personalize-user-experience.md).

![Alternativet ”Utökad tabbsekvens”](media/8c0f12bbb3f26032997ef0ba95d89b6a.png "Alternativet ”Utökad tabbsekvens")

## <a name="form-patterns"></a>Formulärmönster

Nästan 90 procent av sidorna i appen baseras på en mindre mängd mönster. Dessa mönster benämns *formulärmönster*. Varje mönster i formuläret används för att tillhandahålla de åtgärder som utförs oftast på sidan. Ett formulärmönster hjälper till att säkerställa förtrogenhet och lättförståelighet, detta eftersom vanligt förekommande åtgärder och data alltid visas på samma plats på olika sidor. Tack vare det ringa antalet formulärmönster kan användare enkelt lära sig systemet oavsett antal sidor, samt använda det på ett självsäkert sätt när de väl känner igen formulärmönstrena.

Mer information om formulärmönster finns i [Formulärformat och -mönster](../../dev-itpro/user-interface/form-styles-patterns.md).

## <a name="responsive-layout"></a>Responsiv layout

Produkten är avsedd att fungera på olika enheter och med olika formulärfaktorer, från de minsta skärmarna till stora skärmar som har den högsta upplösningen. Vår responsiva layoutmotor låter användare zooma in till en förstoringsnivå på 200 procent (eller, i vissa fall, mer än 200 procent).

## <a name="guidance-to-help-developers-and-customers-incorporate-accessible-thinking-in-their-customizations"></a>Riktlinjer för att hjälpa utvecklare och kunder att inkorporera tillgänglighetstänk i sina anpassningar

Mer information om Microsofts bästa praxis för att aktivera hjälpmedel finns [Hjälpmedel i formulär, produkter och kontroller](../../dev-itpro/user-interface/enable-accessibility.md).