---
title: Artikelbehov för serviceorder
description: Denna artikel beskriver artikelbehov för serviceorder.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 376cda6bbe1800611e6f24c347b9035469a30a14
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015184"
---
# <a name="service-order-item-requirements"></a>Artikelbehov för serviceorder

[!include [banner](../includes/banner.md)]

Du kan du skapa en serviceorder för att följa och hantera tjänster som du tillhandahåller dina kunder. Om du behöver reservera specifika artiklar för en serviceorder kan du skapa lagerartikelkrav för den. Ett artikelbehov kan förbrukas omedelbart från lagret eller så kan det initiera en produktionsorder för artikeln.

Genom att använda ett artikelbehov i stället för en artikeltransaktion kan du planera för inleverans precis innan artikeln verkligen används, skapa en inköpsorder, ta med artikeln i handelsavtalsramverket och ta med artikelbehovet i produktionsplaneringen.

Artikelbehov för serviceorder bearbetas via ett projekt. För att kunna skapa ett artikelbehov på en serviceorder måste serviceordern ha kopplats till ett projekt.

Så snart ett artikelbehov har skapats för en serviceorder kan det visas från **Projekt** på den enskilda serviceordern eller via formuläret **Försäljningsorder**.

## <a name="view-an-item-requirement-from-a-service-order"></a>Visa ett artikelbehov från en serviceorder

1. Klicka på **Servicehantering** \> **Serviceorder** \> **Serviceorder**.
1. Klicka på **Varuutförsel**, och klicka sedan på **artikelbehov** öppna formuläret **artikelbehov**.
1. Klicka på fliken **Projekt** och markera fältet **Serviceorder** om du vill visa serviceorder för artikelbehovet.

## <a name="delete-service-orders-with-item-requirements"></a>Ta bort serviceorder med artikelbehov

Om ett artikelbehov har skapats på en serviceorder kan du inte ta bort serviceordern. Du måste ta bort artikelbehovet innan du kan ta bort serviceordern.

1. Klicka på **Servicehantering** \> **Serviceorder** \> **Serviceorder**.
1. Klicka på **Varuutförsel**, och klicka sedan på **artikelbehov** öppna formuläret **artikelbehov**. Detta formulär visar en lista med alla artikelbehov som har skapats på serviceordern.
1. Välj det artikelbehov som ska tas bort och klicka sedan på **Ta bort**.

–eller–

1. Gå till **Projekthantering och redovisning** \> **Projekt** \> **Alla projekt**.
1. Öppna projektet som har serviceordern där ett artikelbehov har skapats.
1. I formuläret **projekt** i det högra fönstret klickar du på **artikelbehov**. Formuläret **Artikelbehov** öppnas och visar en lista med artikelbehov som associeras med det valda projektet.
1. Välj det artikelbehov som ska tas bort och klicka sedan på **Ta bort**.

## <a name="see-also"></a>Se även

[Artikelbehov (formulär)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))



[!INCLUDE[footer-include](../../includes/footer-banner.md)]