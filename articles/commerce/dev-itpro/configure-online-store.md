---
title: Konfigurera onlinebutiker
description: Denna artikel innehåller länkar till avsnitt som hjälper dig att centralt konfigurera och hantera en onlinebutik.
author: kfend
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: 31541
ms.assetid: 7a25f9b4-a0bb-4e8c-95c0-c0799ec0620d
ms.search.region: Global
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 7840a91d1035f06d2cca93d75df20a157a55f14d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791213"
---
# <a name="configure-online-stores"></a>Konfigurera onlinebutiker

[!include [banner](../includes/banner.md)]

Denna artikel innehåller länkar till avsnitt som hjälper dig att centralt konfigurera och hantera en onlinebutik.

Avsnitten nedan hjälper dig att konfigurera handelskomponenter och onlinebutiken i klienten.

## <a name="configure-an-online-store"></a>Konfigurera en onlinebutik

| Uppgift                                                | Detaljer                                                                                                                                                                                                                                                                                                                                                   | Ämnen                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurera komponenter.                        | Skapa och underhåll information för handelsåtgärder. Denna information omfattar butiker, skatter, produkter, presentkort, kampanjer och rabatter.                                                                                                                                                                                                          | [Skapa och underhålla butik butik](https://technet.microsoft.com/library/hh597201.aspx) (TechNet-innehåll för Microsoft Dynamics AX 2012)                                                                                                                                                                                                                                                                                          |
| Skapa en navigeringshierarki för kanal.    | Skapa en kategorihierarki för kanalnavigering om du vill skapa en kategoristruktur för produkter som du erbjuder via en nätbutik. Du definierar kategorihierarkin och tilldelar sedan produkter, produktattributgrupper och attributvärden till kategorierna. Tilldela sedan kategorihierarkin till en nätbutik.                            | [Skapa en butikshierarki](https://technet.microsoft.com/library/hh580593.aspx)</br> (TechNet-innehåll för AX 2012)</br> [Ställ in attribut och attributtyper](https://technet.microsoft.com/library/hh227548.aspx) (TechNet-innehåll för AX 2012)</br> [Ställ in butiksattributgrupper](https://technet.microsoft.com/library/jj728713.aspx) (TechNet-innehåll för AX för 2012) |
| Lägg till nätbutik i organisationshierarkin. | Innan du kan tilldela produktsortiment eller expedierar order för den nätbutik som du har skapat, eller skapa rapporter som innehåller information från denna nätbutik, måste du tilldela butiken till en eller flera organisationshierarkier. Som minimum måste du tilldela onlinebutiken en organisationshierarki som innehåller produktsortiment. | [Skapa en nätbutik](https://technet.microsoft.com/library/jj682095.aspx) (TechNet-innehåll för AX 2012)                                                                                                                                                                                                                                                                                                     |
| Lägg till leveranssätt i nätbutiken.          | Välj de leveransmetoder som nätbutiken erbjuder.                                                                                                                                                                                                                                                                                                 | [Skapa en nätbutik](https://technet.microsoft.com/library/jj682095.aspx) (TechNet-innehåll för Microsoft AX 2012)                                                                                                                                                                                                                                                                                                     |
| Mappa attribut och lägg till metadata.                   | Välj de alternativ som anger hur attributen för respektive kategori eller kanalprodukt ska fungera i nätbutiken på SharePoint-webbplatsen.                                                                                                                                                                                              | [Skapa en nätbutik](https://technet.microsoft.com/library/jj682095.aspx) (TechNet-innehåll för AX 2012)                                                                                                                                                                                                                                                                                                     |

## <a name="configure-online-store-products"></a>Konfigurera produkter för nätbutik

| Uppgift                                 | Detaljer                                                                                                                                           | Ämnen                                                                                                                                                                                                                                                                            |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Lägg till sortiment i nätbutiken. | Lägg till de sortiment som innehåller de produkter som du erbjuder i nätbutiken.                                                                  | [Skapa en nätbutik](https://technet.microsoft.com/library/jj682095.aspx) (TechNet-innehåll för AX 2012)                                                                                                                                              |
| Hantera kataloger.                     | Använd produktkataloger för att identifiera de produkter som du vill erbjuda i dina butiker.                                                              | [Huvuduppgifter: Skapa produktkataloger för butiker](https://technet.microsoft.com/library/jj728712.aspx) (TechNet-innehåll för AX 2012)                                                                                                                           |
| Hantera priser.                       | Skapa och använd prisgrupper, som är en central länk mellan priser och rabatter, samt kanaler, kataloger, anknytningar och bonusprogram. | [Ställa in priser med hjälp av prisgrupper](https://technet.microsoft.com/library/hh597169.aspx) (TechNet-innehåll för AX 2012)</br> [Ställa in moms](https://technet.microsoft.com/library/hh580571.aspx) (TechNet-innehåll för AX 2012) |
| Hantera rabatter.                    | Ställ in och hantera prisjusteringar och fyra typer av rabatter.                                                                                  | [Skapa prisjusteringar och rabatter](https://technet.microsoft.com/library/hh597114.aspx) (TechNet-innehåll för AX 2012)                                                                                                                          |
| Hantera leveransavgifter.             | Ställ in och hantera leveransavgifter som avser nätbutiken.                                                                     | [Ställ in leveranskostnader för nätbutiker](https://technet.microsoft.com/library/jj728714.aspx) (TechNet-innehåll för AX 2012)                                                                                                                           |
| Hantera leveranssätt.            | Hantera de leveranssätt som är tillgängliga i nätbutiken.                                                                                        | [Ange leveranssätt](https://technet.microsoft.com/library/jj728719.aspx) (TechNet-innehåll för AX 2012)                                                                                                                                            |

## <a name="set-up-data-exchange-between-commerce-and-the-online-store"></a>Ställ in utbyte av data mellan Handel och nätbutiken

| Uppgift                                 | Detaljer                                                                                                                               | Ämnen                                                                                                                                                                                                                                                                                  |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ställ in profiler för kanalintegration. | Profiler gör att komponenterna kan kommunicera med varandra. Skapa profiler innan du konfigurerar inställningar för utbyte av data. | [Konfigurera en profil fr realtidstjänst](https://technet.microsoft.com/library/hh580631.aspx) (TechNet-innehåll för AX 2012)</br> [Konfigurera en kanalprofil](https://technet.microsoft.com/library/jj677402.aspx) (TechNet-innehåll för AX 2012) |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]