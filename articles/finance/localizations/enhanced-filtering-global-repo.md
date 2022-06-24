---
title: RCS-utökad filtrering i den globala RCS-databasen
description: I den här artikeln beskrivs förbättrade filtreringsfunktioner för den globala RCS-databasen, som har förbättrats för att inkludera ytterligare filter.
author: JaneA07
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: a343b9f1af68a727cb2a8d1e390f85e10aab2d39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901224"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>RCS-utökade filtreringsalternativ för att hitta konfigurationer i RCS/globala databasen

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs förbättrade filtreringsfunktioner för den globala RCS-databasen (Regulatory Configuration Services), som har förbättrats för att inkludera möjlighet att filtrera med följande kriterier: 
- **Land/region** – baserad på ISO-landskoder  
- **Tagga** typer för:
  - Funktionellt område
  - Funktionsområde
  - Bransch 
  - Affärsdokument 

För att göra det lättare att upptäcka specifika eller relaterade konfigurationer kan du använda filter, antingen individuellt eller som en grupp. Om du till exempel vill söka efter en enskild typ av "konfigurerbara affärsdokument som är relaterade till leverantörs fakturor, kan använda filtret **affärsdokumenttyp** för att söka efter den typen av dokument. 

[![Filteravsnitt för global databas.](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

Du kan förfina sökningen ytterligare genom att välja dokumenttyp, till exempel leverantörsfaktura och klicka på **Använd filter**. I följande exempel visas resultatet när du filtrerar **affärsdokumenttypen** med dokumenttypen tillagd. 

[![Använt filter och Importera för affärsdokumenttyp.](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

Filtrerade resultat kan importeras till en användares RCS-databas eller en Dynamics 365 Finance-miljö, antingen individuellt eller som en uppsättning. Det gör du genom att markera gruppen med konfigurationer och klicka på **importera**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]