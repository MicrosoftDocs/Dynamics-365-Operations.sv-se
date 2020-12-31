---
title: Generera ett överföringsdokument för en intern lageröverföring
description: I den här proceduren visas hur du skapar överföringsdokument för varurörelser i ett företag.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTransferOrders, InventLocationIdLookup, TransportationDocument, HcmWorkerLookUp, SrsReportViewerForm, InventTransferParmShip
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5cb0d3d51bf30717f05a4daf1a098565d5d48621
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448032"
---
# <a name="generate-a-transfer-document-for-an-internal-inventory-transfer"></a>Generera ett överföringsdokument för en intern lageröverföring

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar överföringsdokument för varurörelser i ett företag. Denna procedur är bara tillgänglig för juridiska personer med en primär adress i Litauen. Proceduren skapades med hjälp av demonstrationsdataföretaget DEMF, med primär adress i Litauen. Innan du kan slutföra denna procedur måste du först slutföra proceduren "Set up transfer documents for goods movement inside a company". Proceduren är avsedd för lagerredovisare. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="create-a-transfer-order"></a>Skapa en överföringsorder
1. Gå till Inventory management > Inbound orders > Transfer order.
2. Klicka på Ny.
3. Ange eller välj ett värde i fältet Från lagerställe.
4. Ange eller välj ett värde i fältet Till lagerställe.
5. Klicka på Lägg till.
6. Markera vald rad i listan.
7. Ange eller välj ett värde i fältet Artikelnummer.

## <a name="enter-transportation-details-for-the-transfer-order"></a>Fyll i transportinformation för överföringsordern
1. Klicka på Spara.
2. Klicka på Ship i åtgärdsfönstret.
3. Klicka på Transportation details.
4. Välj Yes i fältet Print transportation details.
5. Ange eller välj ett värde i fältet Goods issued by.
6. Ange ett värde i fältet Package.
7. Ange ett värde i fältet Risk level of the load.
8. Ange eller välj ett värde i fältet Carrier.
9. Ange eller välj ett värde i fältet Model.
10. Ange ett värde i fältet Registration number.
11. Ange ett värde i fältet Trailer registration number.
12. Ange eller välj ett värde i fältet Driver.
13. Ange ett värde i fältet Driver name.
14. Klicka på Spara.
15. Stäng sidan.

## <a name="view-the-packing-slip-for-the-unposted-transfer-order"></a>Visa följesedeln för den ej bokförda överföringsordern
1. Klicka på Följesedel.
2. Klicka på OK.
3. Stäng sidan.

## <a name="view-the-packing-slip-for-the-posted-transfer-order"></a>Visa följesedeln för den bokförda överföringsordern
1. Klicka på Transfer order i åtgärdsfönstret.
2. Klicka på Ship i åtgärdsfönstret.
3. Klicka på Ship transfer order.
4. Klicka på fliken Allmänt.
5. Markera ett alternativ i fältet Update.
6. Klicka på fliken Översikt.
7. Skriv ett värde i fältet Följesedel.
8. Klicka på OK.
9. Klicka på Ship i åtgärdsfönstret.
10. Klicka på Följesedel.
11. Klicka på OK.

