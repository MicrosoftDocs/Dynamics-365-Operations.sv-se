---
title: Karantänorder
description: Denna artikel beskriver hur du använder karantänorder för att blockera lager.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e18735117d1f671e0efc0947248bbe266fa0ca6
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065612"
---
# <a name="quarantine-orders"></a>Karantänorder

[!include [banner](../includes/banner.md)]

Denna artikel beskriver hur du använder karantänorder för att blockera lager.

Med karantänorder kan du spärra lager. Du kanske vill sätta artiklar i karantän på grund av kvalitetskontroll. Lager som har varit i karantän överförs till ett karantänlagerställe.

> [!NOTE]
> Om du använder lagerstyrningsprocesser (i modulen Lagerstyrning) används bearbetning i karantänorder endast för returförsäljningsorder.

## <a name="quarantine-on-hand-inventory-items"></a>Sätta lagerbehållningsartiklar i karantän

När du sätter objekt i karantän kan du antingen skapa karantänorder manuellt eller konfigurera systemet för att skapa dem automatiskt under inkommande bearbetning.

Om du vill konfigurera systemet att automatiskt generera karantänorder följer du dessa steg.

1. Gå till **Lagerhantering \> Inställningar \> Lager \> Modellgrupper för artiklar**.
1. Välj en relevant modellgrupp i listfönstret eller skapa en ny modellgrupp.
1. På snabbfliken **Lagerpolicyer** väljer du kryssrutan **Karantänhantering**.
1. Stäng sidan.
1. I fältet **Karantänlagerställe** för mottagande lagerställen anger du ett förvalt karantänlagerställe.

När en artikel som registreras som inleverans på lagerstället tillhör en modellgrupp där kryssrutan **Karantänhantering** har valts, kommer systemet att generera en karantänorder för den. Karantänordern ger medarbetare instruktioner att flytta artikeln till karantänlagerstället.

När du skapar karantänorder manuellt på sidan **Karantänorder** måste inte artikeln vara inställd för karantänhantering i den associerade artikelmodellgruppen. För den här processen måste du ange lagerbehållning som ska finns i karantän och karantänlagerstället som ska användas. Du kan använda karantänorderstatusen för att planera processen.

## <a name="quarantine-order-statuses"></a>Karantänorder status

Karantänorder kan ha följande status:

- Skapad
- Startat
- Rapporterat som färdigt
- Avslutat

### <a name="created"></a>Skapad

När en karantänorder skapats manuellt, men posten är inte lagt i karantänlagerställe, karantänordern har status **Skapad**. Två lagertransaktioner skapas. En transaktion är en utlevererad transaktion som kan ha status **Har beställts**, **Fysiskt reserverat**, eller **Plockad**. Den andra transaktionen är en inleveranstransaktionen som kan ha statusen **Beställd** eller **Registrerad** vid karantänlagerstället. Du kan reservera, plocka och registrera uppdateringar i lagret med vanliga processer.

### <a name="started"></a>Startat

När en karantänorder har statusen **Startat** lagret överförs från det vanliga lagret till karantänlagerstället och två lagertransaktioner skapas. En transaktion har status **dras av** och den andra transaktionen har status **Mottaget**. Samtidigt två lagertransaktioner skapas för att hantera transfer tur och retur. Dessa transaktioner är inte daterade. En transaktion har status **Reserverad fysiska**, och den andra transaktionen har status som **beställts**.

### <a name="reported-as-finished"></a>Rapporterat som färdigt

Om du vill rapportera en startad karantänorder som färdig, öppnar du ordern och väljer **Rapportera som färdig** i åtgärdsfönstret. Posten är frisläppt från karantänen men ännu inte flyttad tillbaka till det vanliga lagerstället. Förflyttningen tillbaka till det vanliga lagerstället kan bearbetas via en journal för artikelinförsel som kan initieras under rapporteringen som en färdig process.

### <a name="ended"></a>Avslutat

När en karantänorder avslutas, objektet flyttas från karantänlagerstället tillbaka till vanliga lagret. Status för objekt transaktion *säljs* på karantänlagerställe och *köpas* på regelbundna lager.

## <a name="quarantine-order-scrap"></a>Karantänorder skrot

Som en del av karantänorderprocessen du kan kassera lagerartiklar. När du bearbetar kassationer kommer lagerstatusen att anges som *Sålt* genom en ärendetransaktion från karantänlagerstället.

## <a name="additional-resources"></a>Ytterligare resurser

- [Lagerspärr](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
