---
title: Generera fakturarader när du importerar leverantörsfakturor
description: I den här artikeln beskrivs funktioner för automatisk generering av fakturarader på leverantörsfakturor när fakturor importeras.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5cb2c1234de03e9777921c18e4cbb81eec7feef9
ms.sourcegitcommit: 9c637bcf4e2eb8f711290a861492f038feaf1568
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/09/2022
ms.locfileid: "9462285"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Generera fakturarader när du importerar leverantörsfakturor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I den här artikeln beskrivs funktioner för automatisk generering av fakturarader på leverantörsfakturor när fakturor importeras.

Ibland kan leverantörsfakturor innehålla begränsad information, till exempel information om mottagare och delsummor. De innehåller dock ingen information för radartiklar. När du importerar fakturor kommer fakturarader att genereras automatiskt, baserat på information om motsvarande inköpsorder.

Följ dessa steg om du vill att fakturarader ska kunna skapas automatiskt.

1.  Gå till **Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**.
2.  På fliken **Automation av leverantörsfaktura**, under **Skapa rad automatiskt för importerade fakturor**, ange alternativet **Skapa fakturarader automatiskt** till **Ja**. 
4.  I fältet **Välj standardkvantitet för att skapa automatiska fakturarader** väljer du den kvantitet som ska användas för att generera fakturarader automatiskt:

    - **Beställd kvantitet** – Rader genereras från inköpsorderrader. Det här värdet är standardvärdet.
    - **Produktinleveranskvantitet** – Inköpsordernumret används för att hitta relevanta produktinleveranser. Därefter används produktinleveranskvantiteterna för att generera fakturarader.

## <a name="data-entity-changes"></a>Dataenhet ändras

För att stödja den funktionalitet som beskrivs i den här artikeln, dataenheten **Leverantörsfakturahuvud** har förbättras. Tre fält har lagts till:

- **HeaderOnlyImport** – Detta fält måste ställas in på **Ja** för att generera rader för fakturarubriker.
- **PurchIdRange** – Listan med inköpsordernummer. Fakturanumren kan vara ett intervall, t.ex. **PO0001..PO0009** (där två punkter separerar början och slutet av intervallet), eller diskreta värden, som t.ex. **PO0001, PO0003, PO0006**. Alla inköpsorder måste tillhöra samma leverantörskonto i fakturahuvudet. Annars visas följande felmeddelande: "Det gick inte att generera fakturarader. Inköpsorder har olika leverantörskonton."
- **PackingslipRange** – Listan över produktinleveransnummer. Leverantörsfakturarader kan skapas utifrån produktinleveranser. Produktinleveransnummer inkluderas normalt inte på leverantörsfakturor. Ange bara produktinleveransnumren i det här fältet om du klart kan identifiera vilka produktinleveranser som specifika fakturor är för. Fakturarader kan genereras baserat på produktinleveranser. Om detta fält används ignoreras inställningen av fältet **Välj standardkvantitet för att skapa automatiska fakturarader** på sidan **Parametrar för leverantörsreskontra**. 

**Begränsning**: Om du anger flera produktinleveransnummer skapas flera pågående leverantörsfakturor med samma fakturanummer. Du måste konsolidera dem manuellt innan du bearbetar fakturan ytterligare. I framtida versioner planerar vi att konsolidera fakturorna automatiskt, varför begränsningen tas bort.

Alla produktinleveranser måste tillhöra samma leverantörskonto i fakturahuvudet.

## <a name="result"></a>Resultat

Om rader genereras loggas följande meddelande i historiken för leverantörsfakturaautomatisering: "Skapa fakturarader automatiskt: Lyckades".

Om raderna inte genereras loggas följande felmeddelande: "Skapa fakturarader automatiskt: Misslyckades".
