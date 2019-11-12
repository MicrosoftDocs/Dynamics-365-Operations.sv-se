---
title: Projektförsäljningsorder för tid- och materialprojekt
description: Det här avsnittet beskriver hur du skapar projektbaserade försäljningsorder för tids- och materialprojekt.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: 2f27e3e0a2d6aadc4c5224b55f8a416cbe4e83aa
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551212"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a>Projektförsäljningsorder för tid- och materialprojekt

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

I det här avsnittet beskriver hur du skapar en försäljningsorder för ett projekt. Försäljningsorder kan endast skapas för projekt av typen **tid och material**.

Om ett tids- och materialprojekt har flera finansieringskällor för projektkontraktet, måste du aktivera parametern **Tillåt försäljningsorder för projekt som har flera finansieringskällor** på sidan **Projekthantering och redovisningsparametrar**. 

> [!NOTE]
> - Stöd för projektförsäljningsorder med flera finansieringskällor är tillgänglig från och med programutgåva 10.0.2 och högre.
> - Parametern för att aktivera stöd för projektförsäljningsorder med flera finansieringskällor tas bort i versionen april 2020 och sedn är funktionen alltid aktiverad.

Du kan skapa projektbaserade försäljningsorder på två sätt:

- Gå till själva projektet. I åtgärdsfönstret, välj **Hantera > artikeluppgifter > försäljningsorder**. Projektinformationen används som standard till försäljningsordern från projektet. Projektkontraktet har mer än en finansieringskälla, du behöver välja finansieringskälla för att ange kunden för försäljningsordern. Om det bara finns en finansieringskälla för projektet, anges kunden automatiskt.
- Gå till listsidan **Alla försäljningsorder** och skapa en ny försäljningsorder. Du måste välja projektet för försäljningsordern. När projektet väljs anges kunden från finansieringskällan eller så behöver du välja finansieringskälla om projektkontraktet som har flera finansieringskällor.

