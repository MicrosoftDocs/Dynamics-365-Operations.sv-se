---
title: Konfigurera betalsätt för kundkonto på B2B-näthandelssajter
description: I det här avsnittet beskrivs hur du konfigurerar betalsättet för kundkonto för B2B-näthandelssajter.
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 754e2f83d6c8ff5d3698d98062e54bba7ccd9836
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035966"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Konfigurera betalsätt för kundkonto på B2B-näthandelssajter

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar betalsättet för kundkonto för B2B-näthandelssajter.

Återförsäljare kan acceptera olika typer av betalning i utbytet mot de produkter och tjänster man säljer i en näthandelskanal. Varje betalningstyp som en återförsäljare godtar måste konfigureras i Microsoft Dynamics 365 Commerce när systemet installeras. Kundkontots betalsätt (eller "on account") måste stödjas på B2B-näthandelssajter. 

## <a name="prerequisites"></a>Förutsättningar

1. Lägg till betalsättet för kundkonto i Commerce-administrationen.
2. Koppla betalsättet för kundkontot till näthandelskanalen.
3. Kontrollera att **Tillåt a conto** har aktiverats för kunden på **Butik och Handel \> Kunder \> Alla kunder \> Betalningsstandarder** i Commerce-administrationen. Kontrollera också att parametrarna för **Kreditgräns** har angetts korrekt för kunden på **Butik och Handel \> Kunder \> Alla kunder \> Kredit och inkasso** i Commerce-administrationen. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Aktivera betalsättet för kund i Commerce-webbplatsbyggaren 

För att aktivera betalsättet för kund i Commerce-webbplatsbyggaren följer du dessa steg.

1. Gå till **Webbplatsinställningar \> Tillägg**.
1. Ställ in egenskapen **Aktivera kundkontobetalningar** som **Aktiverad för B2B-kunder**. 
1. Välj **Spara och publicera**.

> [!NOTE]
> De nya webbplatsinställningarna träder i kraft först när filen app.settings.json har uppdaterats. Mer information finns i [SDK- och modulbiblioteksuppdateringar](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Aktivera betalsättet för kundkonto på kassasidan för B2B-näthandelssajten

Följ dessa steg om du vill aktivera betalsättet för kundkonto på kassasidan för B2B-näthandelssajten.

1. Sök efter och redigera kassasidan eller det fragment som innehåller kassamodulen för B2B-näthandelssajten i Commerce-webbplatsbyggaren.
1. I fältet **Behållare för kassaavsnitt** väljer du **Lägg till modul** innan du lägger till en **Kundkontobetalning**-modul.
1. Placera **Kundkontobetalning**-modulen genom att välja ellipsen (**...**) och sedan **Flytta upp** eller **Flytta ner** efter behov.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Bekräfta att betalsättet för kundkontot har aktiverats och publicerats

För att bekräfta att betalsättet för kundkontot har aktiverats följer du dessa steg.

1. Logga in på näthandelssajten.
1. Lägg till en produkt i kundvagnen.
1. Gå till kassasidan. Du bör se det nya betalsättet **Kundkonto**.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera en B2B-näthandelssajt](set-up-b2b-site.md)

[Skapa org-modellhierarkier för B2B-organisationer](org-model.md)

[Hantera affärspartneranvändare på B2B-näthandelssajter](manage-b2b-users.md)

[Ange produktkvantitetsgränser för B2B-näthandelssajter](quantity-limits.md)

[Uppdateringar av SDK och modulbibliotek](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]