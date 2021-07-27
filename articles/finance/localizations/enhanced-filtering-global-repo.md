---
title: RCS-utökad filtrering i den globala RCS-databasen
description: I det här avsnittet beskrivs förbättrade filtreringsfunktioner för den globala RCS-databasen, som har förbättrats för att inkludera ytterligare filter.
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
ms.openlocfilehash: 0aa172550f86a9918a9aaa811e49cb20e7befcdb
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359259"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>RCS-utökade filtreringsalternativ för att hitta konfigurationer i RCS/globala databasen

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs förbättrade filtreringsfunktioner för den globala RCS-databasen (Regulatory Configuration Services), som har förbättrats för att inkludera möjlighet att filtrera med följande kriterier: 
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