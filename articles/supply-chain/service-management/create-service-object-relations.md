---
title: Skapa serviceobjektrelationer
description: Det här avsnittet beskriver hur du kan skapa serviceobjektrelationer för ett serviceavtal och en serviceorder.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 352d3b790da340102b7dbe116d9deeb2f3cbfc4e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437857"
---
# <a name="create-service-object-relations"></a>Skapa serviceobjektrelationer 

[!include [banner](../includes/banner.md)]


Det här avsnittet beskriver hur du kan skapa serviceobjektrelationer för ett serviceavtal och en serviceorder. När du skapar en serviceobjektrelation kopplar du serviceobjektet till serviceavtalet eller serviceordern. När en kund begär service för en artikel som är ett serviceobjekt, kan du välja serviceobjektet från listan med serviceobjektrelationer.

## <a name="create-a-service-object-relation-for-a-service-agreement"></a>Skapa en serviceobjektrelation för ett serviceavtal

Använd följande steg för att skapa en ny serviceobjektrelation för ett serviceavtal:

1.  Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.

2.  I listan **Serviceavtal** markera ett befintligt serviceavtal eller klicka på **Ny** för att skapa ett nytt serviceavtal i listan.

3.  I formuläret **Serviceavtal** på **åtgärdsfönstret**, på fliken **serviceavtal** i gruppen **Relationer**, klicka på **Serviceobjekt**.

4.  I formuläret **Serviceobjekt**, klicka på **Ny** och välj sedan ett serviceobjekt för det här serviceavtalet.

5.  Om du vill tilldela en strukturlista till ett serviceavtal klickar du på **Funktioner** och väljer sedan **Bifoga mallstrukturlista**. I formuläret **Välj strukturlistemall** i fältet **Mallstrukturlista**, välj en mall. 

## <a name="create-a-service-object-relation-for-a-service-order"></a>Skapa en serviceobjektrelation för en serviceorder

Använd följande steg för att skapa en ny serviceobjektrelation för ett serviceorder:

1.  Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.

2.  I listan **Serviceorder** väljer du en befintlig serviceorder eller skapar en ny serviceorder.

3.  I formuläret **Serviceorder** på **åtgärdsfönstret**, på fliken **serviceorder** i gruppen **Relationer**, klicka på **Serviceobjekt**.

4.  I formuläret **Serviceobjekt**, klicka på **Ny** och välj sedan ett serviceobjekt för det här serviceordern.

5.  Om du vill tilldela en strukturlista till ett serviceavtal klickar du på **Funktioner** och väljer sedan **Bifoga mallstrukturlista**. I formuläret **Välj strukturlistemall** i fältet **Mallstrukturlista**, välj en mall. 


## <a name="see-also"></a>Se även

[Serviceobjekt – översikt](service-objects.md)

[Serviceobjektrelationer](service-object-relations.md)

[Strukturlistemallar](template-boms.md)

  


