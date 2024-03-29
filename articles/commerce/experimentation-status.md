---
title: Granska status för ett experiment
description: Denna artikel förklarar vilken status ett experiment har i testcykeln i Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 818435a7c901d2a6b876b9c9db27faffc8b322fc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877259"
---
# <a name="review-the-status-of-an-experiment"></a>Granska status för ett experiment
Det finns många steg när du konfigurerar och kör ett experiment i Dynamics 365 Commerce. Mer information om livscykeln för experiment finns i avsnittet [Experiment i Dynamics 365 Commerce](experimentation-overview.md).

Om du vill veta var ett experiment är i livscykeln i Commerce webbplatsskaparen väljer du **Experiment** i vänster navigeringsfönster. En lista med experiment visas med status för varje experiment i både Commerce och den tredjepartstjänst som används för att skapa experiment, tilldela varianter och analysera data.

I kolumnen **Commerce-status** kan följande värden visas: 
- **Utkast** – experimentet ansluts till en sida eller ett fragment i Commerce och redigeras.
- **Publicerad** – experimentvarianterna är klara att visas på din webbplats. Om experimente kör- i tredjepartstjänsten kommer webbplatsanvändarna att se en variant av sidan eller fragmentet som det har valts av tjänsten från tredjepartstjänst.
- **Opublicerad** – experimentet är inte längre tillgängligt på din webbplats. Webbplatsanvändare ser endast standardversionen av sidan eller fragmentet även om experimentet körs i tredjepartstjänst.
- **Slutförd** – experimentet har utfört kursen och en variant har befordrats till publicerat för alla webbplatsanvändare.

På liknande sätt i kolumnen **tredje parts status** kan följande värden visas för att ange vilken i status experimenten är i tredjepartstjänsten.
- **Utkast** – experimentet ställs in i tjänsten för tredje part, men har inte startats.
- **Körs** – experimentet har startats i tjänsten från tredje part och samlar in data.
- **Pausad** – experimentet pausas och data samlas inte in. Du måste återuppta experimentet för att samla in data på nytt.
- **Arkiverad** – experimentet har varit självklart och har katalogiserats i den tredjepartstjänst för framtida bruk.

I diagrammet nedan visas båda uppsättningarna med status och hur de relaterar till varandra.

[ ![Experimentstatus.](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)


[!INCLUDE[footer-include](../includes/footer-banner.md)]