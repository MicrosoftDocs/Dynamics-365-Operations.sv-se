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
ms.openlocfilehash: d19ee9de70cd14c78a997b7a87c10b53ab3917b0
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "3249103"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a>Projektförsäljningsorder för tid- och materialprojekt

[!include[banner](../includes/banner.md)]

I det här avsnittet beskriver hur du skapar en försäljningsorder för ett projekt. Försäljningsorder kan endast skapas för projekt av typen **tid och material**.

Om ett tids- och materialprojekt har flera finansieringskällor för projektkontraktet, måste du aktivera parametern **Tillåt försäljningsorder för projekt som har flera finansieringskällor** på sidan **Projekthantering och redovisningsparametrar**. 

> [!NOTE]
> - Stöd för projektförsäljningsorder med flera finansieringskällor är tillgänglig från och med programutgåva 10.0.2 och högre.
> - Parametern för att aktivera stöd för projektförsäljningsorder med flera finansieringskällor tas bort i versionen april 2020 och sedn är funktionen alltid aktiverad.

Du kan skapa projektbaserade försäljningsorder på två sätt:

- Gå till själva projektet. I åtgärdsfönstret, välj **Hantera > artikeluppgifter > försäljningsorder**. Projektinformationen används som standard till försäljningsordern från projektet. Projektkontraktet har mer än en finansieringskälla, du behöver välja finansieringskälla för att ange kunden för försäljningsordern. Om det bara finns en finansieringskälla för projektet, anges kunden automatiskt.
- Gå till listsidan **Alla försäljningsorder** och skapa en ny försäljningsorder. Du måste välja projektet för försäljningsordern. När projektet väljs anges kunden från finansieringskällan eller så behöver du välja finansieringskälla om projektkontraktet som har flera finansieringskällor.

