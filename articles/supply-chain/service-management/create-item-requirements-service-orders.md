---
title: Skapa artikelbehov för serviceorder
description: Om du behöver reservera specifika artiklar för en serviceorder kan du skapa lagerartikelkrav för den.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ae44088a1b53ac5e7e9ba09ed7ff611a08d2ed0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996710"
---
# <a name="create-item-requirements-for-service-orders"></a>Skapa artikelbehov för serviceorder 

[!include [banner](../includes/banner.md)]


Du kan du skapa en serviceorder för att följa och hantera tjänster som du tillhandahåller dina kunder. Om du behöver reservera specifika artiklar för en serviceorder kan du skapa lagerartikelkrav för den. Ett artikelbehov kan förbrukas omedelbart från lagret eller så kan det initiera en produktionsorder för artikeln.

Genom att använda ett artikelbehov i stället för en artikeltransaktion kan du planera för inleverans precis innan artikeln verkligen används, skapa en inköpsorder, ta med artikeln i handelsavtalsramverket och ta med artikelbehovet i produktionsplaneringen.

Artikelbehov för serviceorder bearbetas via ett projekt. För att kunna skapa ett artikelbehov på en serviceorder måste serviceordern ha tilldelats till ett projekt. När du har skapat ett artikelbehov för en serviceorder kan du visa artikelbehovet i formuläret **Projekt** för det valda projektet.

## <a name="create-an-item-requirement-for-a-service-order"></a>Skapa ett artikelbehov för en serviceorder

1.  Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.

2.  Välj den serviceorder som du vill skapa ett artikelbehov för.

3.  På **Åtgärdsfönster**, på fliken **Varuutförsel**, klicka på **Artikelbehov**.

4.  I formuläret **Artikelbehov** ange information för krävd artikel. Mer information om ett specifikt fält finns i [Artikelbehov (formulär)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Skapa ett artikelbehov för ett serviceavtal

1.  Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.

2.  Öppna serviceavtalet som du vill skapa ett artikelbehov för.

3.  På snabbfliken **Rader**, klicka på **Lägg till** för att skapa en ny rad.

4.  I fältet **Transaktionstyp**, välj **Artikel**.

5.  I fältet **Artikelinställningar** välj **artikelbehov**.

6.  I fältet **Artikelnummer**, välj den artikel som krävs för serviceavtalet i fältet.

7.  På snabbfliken **raduppgifter** på fliken **produktdimensioner** i fältet **Plats** väljer du lagerplats för artikeln.

8.  Om du vill skapa en serviceorder från avtalsraden, på snabbfliken **Rader** klickar du på **Skapa serviceorder**, och anger sedan relevant information i formuläret **Skapa serviceorder**. 


## <a name="see-also"></a>Se även

[Skapa serviceorder automatiskt](create-service-orders-automatically.md)

  


