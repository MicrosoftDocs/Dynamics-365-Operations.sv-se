---
title: Säljfunktion för kundtjänst
description: Det här avsnittet innehåller en översikt över funktionen för callcenterförsäljning i Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16361
ms.assetid: c8ed2ba4-8d06-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 8b78762ce70b318e1f77e1e49ffaa7b72f01667f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549490"
---
# <a name="call-center-sales-functionality"></a>Försäljningsfunktioner för kundtjänst

[!include [banner](includes/banner.md)]

I Dynamics 365 for Retail, är kundtjänst en typ av butikskanal som kan definieras i programmet. Definiera en viss kanal för dina kundtjänstenheter låter systemet koppla specifika datastandarder och orderhantering är som standard försäljningsorder som har skapats av en användare av kundtjänst.

Kundtjänst omfattar avancerat butikspris och erbjudanden, kataloger, presentkort, bonusprogram och kuponger. Kundtjänstorder utnyttjas också av kassaprogrammet för att ge stöd för scenarier för orderuppfyllelse mellan kanaler.

Det är viktigt att komma ihåg att medan modulen för kundtjänst kan användas inom andra branscher utanför Retail, har den aktuella versionen av kundtjänstprogrammet för Dynamics 365 for Retail inte optimerats för användning i B2B-orderbehandlingsscenarier och scenarier där order har ett stort antal försäljningsrader. Vi rekommenderar att användare som vill använda kundtjänstfunktioner för orderhantering utanför normal transaktionsbearbetning direkt till konsument, ta tillräcklig tid för att testa och verifiera att kundtjänstfunktionerna uppfyller funktionella och prestandabehov.

Förutom att stödja skapande av order ger kundtjänstmodulen även ett användarvänligt kundtjänstprogram som gör det enklare för användare att hitta kundkonton och granska alla relaterade kundorderdata och attribut. Skärmen för kundtjänst har utformats så att användare snabbt får tillgång till orderrelaterade data för att besvara vanliga orderrelaterade frågor som tagits emot från kunder.

Den här sidan innehåller länkar till relevanta handlingar som är relaterade till installation, konfiguration och funktionell användning av kundtjänstfunktionerna i Dynamics 365 for Retail.

## <a name="configure-the-call-center"></a>Konfigurera kundtjänst.

[Ställ in alternativ för orderbearbetning](set-up-order-processing-options.md)

## <a name="configure-order-processing"></a>Konfigurera orderbearbetning

[Ställ in bedrägerivarningar](set-up-fraud-alerts.md)

[Manuella orderspärrar](work-with-order-holds.md)

## <a name="configure-payment-processing"></a>Konfigurera betalningsbearbetning

[Betalningsmetoder i ett kundcenter](work-with-payments.md)

## <a name="configure-delivery-modes"></a>Konfigurera leveranslägen

[Konfigurera leveranslägen och avgifter för kundtjänst](configure-call-center-delivery.md)

## <a name="configure-direct-marketing"></a>Konfigurera direkt marknadsföring

[Kundtjänstkataloger](call-center-catalogs.md)

[Ställa in RFM-analys](set-up-rfm-analysis.md)

## <a name="configure-continuity-programs"></a>Konfigurera kontinuitetsprogram

[Ställ in ett kontinuitetsprogram för en kundtjänst](set-up-continuity-program.md)
