---
title: Koncernintern planering
description: Det här ämnet beskriver koncernintern planering och förklarar hur du konfigurerar koncernintern planering med planeringsoptimering i Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dd498489e18eaba81720757faa14c0bf7b7d67f1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263408"
---
# <a name="intercompany-planning"></a>Koncernintern planering

[!include [banner](../../includes/banner.md)]

För vissa organisationer är logistikoperationer beroende av andra juridiska personer (företag) i organisationen. Dessa operationer hanteras med koncernintern försäljning och inköp eftersom varje juridisk person har en separat kontoplan.

Det här ämnet beskriver koncernintern planering och förklarar hur du konfigurerar koncernintern planering med planeringsoptimering i Microsoft Dynamics 365 Supply Chain Management.

I det här avsnittet används följande viktiga koncerninterna termer:

- **Uppström** – en relativ referens i en firma eller leveranskedja. Den visar rörelsen i råvaruleverantörens riktning.
- **Nedström** – en relativ referens i en firma eller leveranskedja. Den visar rörelsen i kundens riktning.
- **Planerad koncernintern efterfrågan** – planerad efterfrågan för en produkt i ett företag, baserat på planerad efter frågan för produkten från ett underordnat företag.

Vid huvudplanering kan en plan i ett företag inkludera planerad koncernintern efter frågan som är relaterad till planerade order från en plan i ett annat företag. Den här funktionen är användbar eftersom den ger full insyn i planerade order mellan företag. Det säkerställer också att alla begärda planerade leveransorder skapas, utan att kräva att planerade order måste bekräftas för det koncerninterna behovet.

Om du kör huvudplaneringen från en huvudplan som inkluderar planerad efterföljande efterfrågan, tas planerade inköpsorder från de relaterade koncerninterna leverantörerna med i planen som efterfrågan.

## <a name="required-setup"></a>Obligatorisk inställning

Om du vill använda koncernintern planering måste du förbereda systemet på följande sätt:

1. De relevanta produkterna måste frisläppas på alla berörda företag. Mer information finns i [Konfigurera och använd koncernintern handel i Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) på Microsoft Learn.
1. Efterföljande efterfrågan måste täckas av inköp från en leverantör som har en koncernintern relation till det överordnade företaget och relevanta standard lagerdimensioner (webbplats och lagerställe) för kunden. Mer information finns i [Konfigurera och använd koncernintern handel i Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) på Microsoft Learn.
1. Huvudplanen i det överordnade företaget måste inkludera planerad efterföljande efterfrågan och det relevanta företaget och huvudplanen måste anges i de efterföljande planerna.

## <a name="include-planned-downstream-demand"></a>Inkludera underordnad planerad efterfrågan

Följ dessa steg för att konfigurera huvudplanen så att den omfattar planerad efterföljande efterfrågan.

1. Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner**.
1. Välj eller skapa en huvudplan.
1. På snabbfliken **Koncernintern planering** anger du följande fält:

    - **Inkludera planerad efterföljande efterfrågan** – Ange det här alternativet till *Ja* om du vill aktivera koncern internplanering för huvudplanen.
    - **Efterföljande planer** – Om du anger alternativet **Inkludera planerad efterföljande efterfrågan** till *Ja*, använd verktygsfältet och rutnätet för att lägga till önskade huvudplaner från andra företag.

## <a name="peg-across-companies-by-using-multilevel-pegging"></a>Peg över flera företag med hjälp av pegging på flera nivåer

I pegging på flera nivåer kan du visa pegging över flera företag för att visa den initiala källan för efterfrågan som täcks av en tillgång.

Följ stegen nedan om du vill visa pegging-information på flera nivåer.

1. Gå till **Huvudplanering \> Huvudplanering \> Planerade order**.
1. Välj eller öppna en planerad order.
1. I åtgärdsfönstret på fliken **Visa** i gruppen **Krav**, välj **Pegging på flera nivåer**.

### <a name="intercompany-example-that-involves-two-companies"></a>Koncerninternt exempel som inbegriper två företag

I det här exemplet skapas en planerad tillverkningsorder i USMF-företaget för att täcka en försäljningsorder i DEMF-företaget. I USMF är direkt efterfrågan planerad koncernintern efterfrågan. För att denna efterfrågan ska visas i USMF körs huvudplaneringen först i DEMF och sedan i USMF.

Följande illustration visar hur det här exemplet kan visas på sidan **Pegging på flera nivåer** för den planerade tillverkningsordern.

![Koncerninternt exempel som inbegriper två företag](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a>Koncerninternt exempel som inbegriper tre företag

I det här exemplet skapas en planerad inköpsorder i USMF-företaget för att täcka en försäljningsorder i FRRT-företaget. I DEMF- och USMF-företag är direkt efterfrågan planerad koncernintern efterfrågan. För att denna efterfrågan ska visas i USMF körs huvudplaneringen först i FRRT, sedan i DEMF och slutligen i USMF.

Följande illustration visar hur det här exemplet kan visas på sidan **Pegging på flera nivåer** för den planerade tillverkningsordern.

![Koncerninternt exempel som inbegriper tre företag](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]