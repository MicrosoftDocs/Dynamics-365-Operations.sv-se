---
title: Parametrar för globala enheter
description: I det här avsnittet beskrivs hur du ställer in inställningar för mobila enheter på sidan Parametrar för lagerstyrning.
author: Mirzaab
ms.date: 08/13/2021
ms.topic: article
ms.search.form: WHS
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 0ae04c86ff1eafb649fcef7c34ace66bdc3e5cb8
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679177"
---
# <a name="global-mobile-device-parameters"></a>Parametrar för globala enheter

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in parametrar för global hantering av lagerställen som påverkar hur systemet samverkar med mobila enheter.

Mer information om hur du ställer in lagerarbetare finns i [Hantera lagerarbetare](manage-warehouse-workers.md). Detaljerad information om det mottagna ID-numret och hantering på mobila enheter finns i [Inleverans av ID-nummer som erhålls via mobilappen för Warehouse Management](warehousing-mobile-device-app-license-plate-receiving.md). För mer information om processen för rullande inventering se [Rullande inventering](cycle-counting.md) och [Exempelscenarier för rullande inventering](cycle-counting-scenarios.md).

## <a name="open-the-warehouse-management-parameters-page"></a>Öppna sidan Parametrar för lagerstyrning

För att öppna sida **Parametrar för lagerhantering**, gå till **Lagerhantering \> Inställningar \> Parametrar för lagerstyrning**. Du kan sedan ställa in fälten som är relaterade till mobilt arbete, på det sätt som beskrivs i nästa avsnitt i det här avsnittet.

## <a name="mobile-device-fasttab-on-the-general-tab"></a>Snabbflik på den mobila enheten på fliken Allmänt

Inställningarna för den globala enheten finns på snabbfliken **Mobil enhet** på fliken **Allmänt** på sidan **Lagerstyrningsparametrar**.  Följande fält är tillgängliga.

| Fält | beskrivning |
|---|---|
| Noteringstyp för mobil enhet | Välj den typ av information som ska visas för användare under plockning av försäljningsorder. |
| Gräns för skannad kvantitet | Ange den maximala artikelkvantiteten som en arbetare kan skanna under varje session med ett menyalternativ för en mobil enhet som har värdet **Arbetsskapandeprocess** för *Justering i*. Det här fältet påverkar inte skanningar som görs med någon annan typ av menyalternativ. |
| Använd sessionsloggning för mobil enhet | Ställ in det här alternativet till *Ja* om du vill ha en logg över historiken för arbetares inloggning. Om du vill visa loggen går du **Arbetsanvändarsessioner \> Förfrågningar och rapporter \> Loggar för mobila enheter \> Arbetsanvändarsessioner**. |
| Antal lagrade fel | Ange det maximala antalet felposter som ska lagras i systemet. Om du vill visa felloggen går du **Arbetsanvändarsessioner \> Förfrågningar och rapporter \> Loggar för mobila enheter \> Arbetsanvändarsessioner**. |
| Standardjournal för lageröverföring | Välj den journal som används när arbetare använder en mobil enhet för att flytta produkter från ett lagerställe till ett annat. |
| Tillåt registrering av inköpsorderrad vid extern granskning | Ställ in det här alternativet till *Ja* om arbetare ska kunna använda en mobil enhet för att registrera orderrader för inköpsorder som har ett värde **godkännandestatus** för *I extern granskning*. Ange det här alternativet till *Nej* om du vill förhindra att arbetare registrerar rader för inköpsorder som är i extern granskning. |
| Aktivera RSAT-stöd | Fältet aktiverar valideraren för mobilappen Warehouse Management, som loggar och validerar varje steg som programmet utför. Eftersom den här processen kan göra systemets prestanda långsammare bör du bara aktivera valideraren under testningen. Du ska aldrig aktivera den i en produktionsmiljö. |
