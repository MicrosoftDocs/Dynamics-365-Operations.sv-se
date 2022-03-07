---
title: Skapa serviceorder automatiskt
description: Du kan skapa serviceorder som baseras på ett serviceavtal för den giltiga perioden av serviceavtalet.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08fb7363ab87fd6a7f3d38406e72b1f542dc2c2a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437847"
---
# <a name="automatically-create-service-orders"></a>Skapa serviceorder automatiskt 

[!include [banner](../includes/banner.md)]


Du kan skapa serviceorder som baseras på ett serviceavtal för den giltiga perioden av serviceavtalet.

De serviceorder som du skapar från ett serviceavtal kopplas till serviceavtalet.

Serviceorder skapas automatiskt utifrån följande inställningar:

  - Det serviceavtalsintervall som har ställts in på serviceavtalsraderna. Serviceavtalsintervallet anger med vilken frekvens serviceorderrader ska skapas. Mer information om serviceintervall finns i [Serviceintervall](service-intervals.md).

  - Den period du anger för att definiera serviceperioden i fälten **Från datum** och **Till datum** i formuläret **Skapa serviceorder**. Mer information finns i [Skapa serviceorder automatiskt](create-service-orders-automatically.md).

  - Alternativet **kombinera serviceorder** i serviceavtalshuvudet. Alternativet anger om de serviceorderrader som skapas från ett serviceavtal ska kombinera serviceorder efter medarbetare, serviceuppgift, serviceobjekt eller serviceavtal. Mer information finns i [kombinera serviceorder](combine-service-orders.md).

  - Alternativet **Tidsfönster** på serviceavtalsraden. Tidsfönstret anger hur långt en serviceorderrad kan utsträckas i tiden i relation till radens beräknade datum. Mer information finns i [tidsfönster](time-windows.md).


> [!NOTE]
> <P>Om den dag som har angetts för en serviceorder inte är öppen i den kalender som du har valt i formuläret <STRONG>Servicehanteringsparametrar</STRONG> visas ett meddelande om att det finns en kalenderkonflikt. Du kan ignorera meddelandet och serviceordern skapas även om dagen är stängd i kalendern.</P>

## <a name="example-1"></a>Exempel 1

Serviceavtalet varar från 1 januari 2012 till 31 december 2012. Om den serviceperiod som du anger i formuläret **skapa serviceorder** är från 1 november 2012 fram till den 1 februari 2013 skapas serviceorder från 1 november 2012 till 31 december 2012.

## <a name="example-2"></a>Exempel 2

Serviceavtalet varar från 1 januari 2012 till 31 december 2012. Det finns två serviceavtalsrader kopplade till serviceavtalet. Första serviceavtalsraden har 2 januari 2012 som startdatum och 1 mars 2012 som slutdatum. Den andra serviceavtalsraden har 1 april 2012 som startdatum och 31 december 2012 som slutdatum. Du kan ange en period i formuläret **skapa serviceorder** från 1 oktober 2012 till 31 December 2012. Detta innebär att serviceorder bara skapas för den andra serviceavtalsraden, eftersom start- och slutdatumen för den första raden ligger före den period som du har angett för serviceordern.

  


