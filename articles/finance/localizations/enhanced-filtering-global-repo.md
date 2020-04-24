---
title: Utökad filtrering i den globala RCS-databasen
description: I det här avsnittet beskrivs förbättrade filtreringsfunktioner för den globala RCS-databasen, som har förbättrats för att inkludera ytterligare filter.
author: JaneA07
manager: AnnBe
ms.date: 03/03/2020
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
ms.openlocfilehash: 1adbd690795139778dc77a574e9d5f91a4bdeb3c
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249175"
---
# <a name="enhanced-filtering-options-for-finding-configurations-in-the-global-repository"></a>Förbättrade filtreringsalternativ för att hitta konfigurationer i den globala databasen

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs förbättrade filtreringsfunktioner för den globala RCS-databasen (Regulatory Configuration Services), som har förbättrats för att inkludera följande filter: 
- **Land/region** - baserad på ISO-landskoder  
- **Taggar** – för funktionellt/funktionsområde. Affärsdokument av branschtyp 

Du kan använda filter, antingen individuellt eller i grupper, för att hitta specifika eller relaterade konfigurationer. Om du till exempel vill hitta alla konfigurerbara affärsdokument som hör till leverantörsfakturor kan du använda filtret för **affärsdokumenttyp**. 

Du kan förfina en sökning ytterligare genom att välja landskoden och klicka på **Använd filter**.  

[![Filteravsnitt för global databas](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

I följande exempel visas resultatet när du filtrerar **affärsdokumenttypen**. 

[![Använt filter och importerar för affärsdokumenttyp](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

Filtrerade resultat kan importeras till användare RCS eller Dynamics 365 Finance-miljön, antingen individuellt eller som en uppsättning (genom att välja gruppen med konfigurationer) och klicka på **importera**.






