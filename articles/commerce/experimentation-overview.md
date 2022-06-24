---
title: Experiment i Dynamics 365 Commerce
description: Experiment gör det möjligt att skapa, redigera och hantera sidlayouter och innehålls behandlingar i webbplatsskaparen. Komplett support för experiment har aktiverats för sidor och enheter för näthandel på en sida.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: overview
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1ef877072ba7ffe1b0326cf8d526b512b5ab30b8
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946224"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Experiment i Dynamics 365 Commerce
Du kan använda experiment i Dynamics 365 Commerce för att validera hypoteser om hur effektiva dina näthandelssidor är och fatta beslut med datadriven säkerhet. Commerce har stöd för A/B-test på sidor, moduler och fragment och gör att du kan mäta effekterna av föreslagna ändringar på webbplatsen.

Du kan skapa, redigera och hantera metoder för sid- och innehållshantering som kallas **varianter** i Commerce webbplatsskaparen. Commerce är integrerad med tjänster från tredje part som du kan använda för att skapa experiment och behandla tilldelningar. Händelseströmmar i realtid som samlas i Commerce aktiverar analysen som definierar experimentresultatet i tredjepartstjänst. Du kan sedan använda dessa analyser för att hjälpa till att stödja eller tillbakavisa din hypotes.

## <a name="set-up-prerequisites"></a>Konfigurera krav

1. **Skaffa rätt version av Commerce** – uppgradera ditt modulbibliotek, rogramutvecklingskit (SDK) och Commerce Scale Unit till Commerce version 10.0.13 eller senare.
1. **Ställ in en experimentanslutning** – en experimentanslutning gör det möjligt för Commerce att ansluta sig till tjänster från tredje part för att hämta experimentlistan och bestämma när ett experiment ska visas för en användare. Du kan köpa en anslutning från en tredje part från [AppSource](https://appsource.microsoft.com). Följ installationsanvisningarna från utgivaren. Du kan alternativt använda testanslutningen från Commerce för att testa experiment arbetsflödet utan att behöva konfigurera en extern tjänst. Mer information finns i [Konfigurera och aktivera anslutningar](e-commerce-extensibility/connectors.md). 
1. **Aktivera experimentfunktionsflaggorna i Commerce** - Du kan aktivera experiment på klientorganisationsnivå genom att gå till **Inställningar för klientorganisation \> Funktioner**, eller på webbplatsnivå på **Webbplatsinställningar \> Funktioner**. Aktivera flaggan **Experimentering** för att börja skapa modulvariationer. Om du inaktiverar den här flaggan visas alla experiment för användarna och alla redigeringsfunktioner i webbplatsskaparen tas bort.
    
## <a name="experimentation-lifecycle"></a>Livscykel för experiment

Att konfigurera ett experiment, skapa varianter och att köra ett experiment är en iterativ process. I diagrammet nedan visas experiment livscykeln i Commerce och tjänsten för tredje part. 

[ ![Livscykel för experiment.](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Mer information om respektive steg i experimentprocessen finns i följande artiklar.
- [Identifiera en hypotes och fastställa mätvärden för ett experiment](experimentation-identify.md)
- [Konfigurera ett experiment](experimentation-setup.md)
- [Ansluta till och redigera ett experiment](experimentation-connect-edit.md)
- [Förhandsgranska och publicera ett experiment](experimentation-preview-publish.md)
- [Köra och övervaka ett experiment](experimentation-run-monitor.md)
- [Höja en variation och slutföra ett experiment](experimentation-review-complete.md)

> [!NOTE]
> Om du vill veta var ett experiment är i livscykeln väljer du **Experiment** i vänster navigeringsfönster i webbplatsskaparen. En lista med experiment visas med status för varje experiment i både Commerce och tjänsten för tredje part. Mer information finns i [Granska status av ett experiment](experimentation-status.md).

## <a name="next-step"></a>Gå vidare
[Identifiera en hypotes och fastställa mätvärden för framgång för ett experiment](experimentation-identify.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
