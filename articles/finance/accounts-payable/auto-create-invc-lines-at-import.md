---
title: Generera fakturarader när du importerar leverantörsfakturor
description: I det här avsnittet beskrivs funktioner för automatisk generering av fakturarader på leverantörsfakturor när fakturor importeras.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 87dec3c142ae296975ab98432421be4548085c80
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647911"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Generera fakturarader när du importerar leverantörsfakturor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs funktioner för automatisk generering av fakturarader på leverantörsfakturor när fakturor importeras.

Ibland kan leverantörsfakturor innehålla begränsad information, till exempel information om mottagare och delsummor. De innehåller dock ingen information för radartiklar. När du importerar fakturor kan systemet automatiskt generera fakturarader, baserat på information om motsvarande inköpsorder.

Följ dessa steg om du vill att fakturarader ska kunna skapas automatiskt.

1.  Gå till **Leverantörsreskontra \> Inställningar \> Parametrar för leverantörsreskontra**.
2.  På fliken **Automation av leverantörsfaktura**, under **Skapa rad automatiskt för importerade fakturor**, ange alternativet **Skapa fakturarader automatiskt** till **Ja**. 
4.  På fältet **Välj standardkvantitet för att skapa automatiska fakturarader** välj den kvantitet som systemet ska använda för att automatiskt generera fakturarader:

    - **Beställd kvantitet** – Systemet genererar rader från inköpsorderrader. Det här värdet är standardvärdet.
    - **Produktinleveranskvantitet** – Systemet använder inköpsordernummer för att hitta relevanta produktinleveranser. Därefter används produktinleveranskvantiteterna för att generera fakturarader.

## <a name="data-entity-changes"></a>Dataenhet ändras

För att stödja den funktionalitet som beskrivs i det här avsnittet, dataenheten **Leverantörsfakturahuvud** har förbättras. Tre fält har lagts till:

- **HeaderOnlyImport** – Detta fält måste ställas in på **Ja** för att systemet ska generera rader för fakturarubriker.
- **PurchIdRange** – Listan med inköpsordernummer. Fakturanumren kan vara ett intervall, t.ex. **INV0001..INV0009** (där två punkter separerar början och slutet av intervallet), eller diskreta värden, som t.ex. **INV0001, INV0003, INV0006**. Alla inköpsorder måste tillhöra samma leverantörskonto i fakturahuvudet. Annars visas följande felmeddelande: "Det gick inte att generera fakturarader. Inköpsorder har olika leverantörskonton."
- **PackingslipRange** – Listan över produktinleveransnummer. Leverantörsfakturarader kan skapas utifrån produktinleveranser. Produktinleveransnummer inkluderas normalt inte på leverantörsfakturor. Ange bara produktinleveransnumren i det här fältet om du klart kan identifiera vilka produktinleveranser som specifika fakturor är för. Fakturarader kan genereras baserat på produktinleveranser. Och om detta fält används, inställningen av fältet **Välj standardkvantitet för att skapa automatiska fakturarader** på sidan **Parametrar för leverantörsreskontra** ignorerades. 

**Begränsning**: Om du anger flera produktinleveransnummer skapas flera pågående leverantörsfakturor med samma fakturanummer. Du måste konsolidera dem manuellt innan du bearbetar fakturan ytterligare. I framtida versioner planerar vi att aktivera systemet för automatisk konsolidering av fakturorna, så begränsningen tas bort.

Alla produktinleveranser måste tillhöra samma leverantörskonto i fakturahuvudet.

## <a name="result"></a>Resultat

Om rader genereras i systemet loggas följande meddelande i historiken för leverantörsfakturaautomatisering: "Skapa fakturarader automatiskt: Påföljande."

Om raderna inte genereras i systemet loggas följande felmeddelande: "Skapa fakturarader automatiskt: Misslyckat."
