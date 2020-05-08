---
title: RCS-utökad filtrering i den globala RCS-databasen
description: I det här avsnittet beskrivs förbättrade filtreringsfunktioner för den globala RCS-databasen, som har förbättrats för att inkludera ytterligare filter.
author: JaneA07
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 1913b661c46af5e34da1a2939cb2a5d5b4e46411
ms.sourcegitcommit: 7df49a85de484d013518217ba8ada6c61da4b6e4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2020
ms.locfileid: "3287949"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>RCS-utökade filtreringsalternativ för att hitta konfigurationer i RCS/globala databasen

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs förbättrade filtreringsfunktioner för den globala RCS-databasen (Regulatory Configuration Services), som har förbättrats för att inkludera möjlighet att filtrera med följande kriterier: 
- **Land/region** - baserad på ISO-landskoder  
- **Tagga** typer för:
  - Funktionellt område
  - Funktionsområde
  - Bransch 
  - Affärsdokument 

För att göra det lättare att upptäcka specifika eller relaterade konfigurationer kan du använda filter, antingen individuellt eller som en grupp. Om du till exempel vill söka efter en enskild typ av "konfigurerbara affärsdokument som är relaterade till leverantörs fakturor, kan använda filtret **affärsdokumenttyp** för att söka efter den typen av dokument. 

[![Filteravsnitt för global databas](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

Du kan förfina sökningen ytterligare genom att välja dokumenttyp, till exempel leverantörsfaktura och klicka på **Använd filter**. I följande exempel visas resultatet när du filtrerar **affärsdokumenttypen** med dokumenttypen tillagd. 

[![Använt filter och importerar för affärsdokumenttyp](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

Filtrerade resultat kan importeras till en användares RCS-databas eller en Dynamics 365 Finance-miljö, antingen individuellt eller som en uppsättning. Det gör du genom att markera gruppen med konfigurationer och klicka på **importera**.
