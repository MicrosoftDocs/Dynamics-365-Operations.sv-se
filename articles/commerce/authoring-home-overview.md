---
title: Översikt över redigeringssidan
description: Det här ämnet innehåller en översikt över redigeringssidan i Microsoft Dynamics 365 Commerce.
author: brendans
ms.date: 10/31/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application USer
ms.reviewer: v-chgri
ms.assetid: ''
ms.search.region: Global
ms.author: brendans
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 68487c899edccaeff9c339d746d21b1d27b498aa
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984631"
---
# <a name="authoring-page-overview"></a>Översikt över redigeringssidan

  
 [!include [banner](includes/banner.md)]

Det här ämnet innehåller en översikt över redigeringssidan i Microsoft Dynamics 365 Commerce.

Webbplatser kan skapas för att stödja olika affärsbehov. De kan representera ett helt företag, erbjuda en enda affärskanal eller rikta en viss målgrupp eller ett specifikt segment till en målgrupp. En tillverkare av kläder kan till exempel ha en webbplats som visar alla varumärken som den äger. Samma tillverkare av kläder kan sedan ha en separat webbplats för vart och ett av dessa varumärken, och även en uppsättning webbplatser som innehåller lyxmodeartiklar, utomhusmode och barnkläder.

Dynamics 365 Commerce har stöd för generering och hantering av flera webbplatser, och varje webbplats kan ha ett eget utseende och innehåll. Redigeringssidan fungerar som en gemensam åtkomstpunkt för dessa webbplatser. Du kan använda den för att logga in och ut ur systemet, och för att skapa nya webbplatser.

För närvarande består redigeringssidan av följande avsnitt.

- **Övre fält** – den översta raden visas högst upp på redigeringssidan. Den ger enkel åtkomst till näthandelsverktyg, meddelanden, supportlänkar och användarinloggning.
- **Kommandofält** – kommandofältet visas under den översta raden. Det kan användas för att skapa nya webbplatser.
- **Platslista** – platslistan fyller allt utrymme nedanför kommandofältet. Den innehåller en omfattande lista med webbplatser och de domäner som är kopplade till dem.

Illustrationen som följer visar redigeringssidan.

![Redigeringssida för Dynamics 365 Commerce.](../commerce/media/authoring_tools_01.png)

## <a name="use-the-home-button-to-select-a-tool"></a>Använd startknappen för att välja ett verktyg

Knappen **Start** visas i det övre vänstra hörnet på redigeringssidan. Den ger enkel åtkomst till andra nät handelsverktyg. När du väljer den här knappen öppnas en meny med de verktyg som du kan använda. När du väljer ett verktyg stängs menyn och det valda verktyget läses in i webbläsaren.

## <a name="view-and-clear-notifications"></a>Meddelanden visa och rensa

Knappen **meddelanden** är en av knapparna i det övre högra hörnet på redigeringssidan. Den ser ut som en klocka. Genom att klicka på den här knappen kan du visa alla meddelanden som har skickats till dig.

Meddelanden används i redigeringsverktyget för att meddela dig när åtgärder har genomförts. Ett meddelande kan till exempel ange "din sida har publicerats" för att informera dig om att en publiceringsåtgärd har genomförts.

Meddelanden kan också informera dig om fel som påträffades när en åtgärd utfördes. Markera felmeddelandet om du vill öppna meddelandet. Informationen i det här meddelandet kan hjälpa dig att lösa felet.

Du kan rensa meddelanden från meddelandemenyn genom att klicka på **Ta bort** längst ned i aviseringsmeddelandet. Om du vill massrensa meddelanden väljer du **Ta bort alla** längst ned på meddelandemenyn.

## <a name="get-help-with-the-authoring-tool"></a>Få hjälp med redigeringsverktyget

Knappen **Hjälp** är en annan knapp i det övre högra hörnet på redigeringssidan. Det ser ut som ett frågetecken. När du väljer den här knappen öppnas en meny med följande fördefinierade alternativ:

- **Hjälp för webbplatsutveckling** – om du väljer det här alternativet öppnas dokumentationen för att skapa en ny webbplats på en ny flik i webbläsaren.
- **Feedback och support** – Välj det här alternativet om du vill öppna en Microsoft Yammer-kanal där du kan lämna feedback om redigeringsverktyget eller begära support.
- **Sekretess och cookies** – om du väljer det här alternativet öppnas Microsofts sekretesspolicy på en ny flik i webbläsaren.
- **Om** – Välj det här alternativet om du vill öppna en meddelanderuta som innehåller information om redigeringsverktyget och den version som du för närvarande använder.

## <a name="sign-in-to-and-out-of-the-authoring-tool"></a>Logga in och ut ur redigeringsverktyget

Knappen **Mitt konto** är en annan knapp i det övre högra hörnet på redigeringssidan. Det ser ut som en färgad cirkel. Om du väljer den här knappen kan du se vilket konto du använde när du loggade in, och du kan också logga ut från kontot efter behov.

Följ de här stegen om du vill logga in på eller ut från redigeringsverktyget.

- Om du inte redan är inloggad på utvecklingsverktyget väljer du **Mitt konto** \> **Logga in** för att logga in.
- Om du redan är inloggad och vill logga ut väljer du **mitt konto** \> **logga ut**.

## <a name="change-the-display-language-of-the-authoring-tool"></a>Ändra visningsspråket för redigeringsverktyget

Du kan också använda knappen **mitt konto** om du vill ändra språket för textsträngarna som visas i utvecklingsverktyget.

För att ändra visningsspråk, följ stegen nedan.

1. Välj **Mitt konto** \> **Ändra språk**. En dialogruta visas.
1. Välj ett av användarspråken och välj sedan **Spara**.

## <a name="create-a-new-website"></a>Skapa en ny webbplats

Dynamics 365 Commerce har stöd för generering och hantering av flera webbplatser, och varje webbplats kan ha ett eget utseende och innehåll.

Gör så här om du vill skapa en ny webbplats.

1. Klicka på **Ny webbplats** i kommandofältet. En dialogruta visas.
2. Ange följande obligatoriska information för den nya webbplatsen:

    - **Namn på webbplats** – Ange namnet på webbplatsen. Det här namnet visas inte för webbplatskunder. Det används i stället i webbplatslistan och andra platser i redigeringsverktyget.
    - **Säkerhetsgrupp för webbplatsadministratörer** – ange det fullständiga namnet på Microsoft Azure Active Directory (Azure AD) säkerhetsgrupp som innehåller de användare som ska ha administrativ behörighet för webbplatsen. Namnet på administratörsgruppen, tillsammans med de övriga behörigheterna för webbplatsen, kan ändras efter att webbplatsen har skapats.
    - **Standardkanal** – ange den standardkanal för marknadsföring som ska associeras med webbplatsen. Standardkanalen avgör vilka produkter som kan säljas via webbplatsen.
    - **Standardspråk** – Välj standardspråket för kanalen när du har angett standardkanalen. Standardkanalen definierar språket som produkter visas i om kunden inte anger något önskat språk.
    - **Standardmarknad** – ange webbplatsens standardmarknad. Standardmarknaden definierar den marknad som visas om kunden inte anger en prioriterad marknad.
    - **Domän** – Välj den webbdomän som ska associeras med webbplatsen. Den här domänen är den domän som webbplatsens kunder ska gå till i webbläsaren.

1. Välj **OK**. Den nya webbplatsen skapas.

> [!NOTE]
> Det kan ta upp till 60 sekunder att skapa en ny webbplats. När processen är klar visas ett meddelande i meddelandefältet. Dessutom visas webbplatsen i platslistan och har det webbplatsnamn som du har angett.

## <a name="select-a-website-to-author"></a>Välj en webbplats att redigera

Webbplatslistan ger en omfattande lista över de webbplatser som är kopplade till näthandelssystemet. Webbplatser visas i alfabetisk ordning. Den domän som är associerad med varje webbplats visas också. Om du vill visa innehållet på en webbplats och starta på författarsidor markerar du webbplatsens namn. Redigeringsverktyget och innehållet för webbplatsen läses in.

När utvecklingsverktyget har lästs in kan du välja **Start** för att gå tillbaka till redigeringssidan.

## <a name="additional-resources"></a>Ytterligare resurser

[Hantera näthandelsanvändare och roller](manage-ecommerce-users-roles.md)

[Språkinformation för sökmotoroptimering (SEO) för din webbplats](search-engine-optimization-considerations.md)

[Hantera säkerhetspolicy för innehåll (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
