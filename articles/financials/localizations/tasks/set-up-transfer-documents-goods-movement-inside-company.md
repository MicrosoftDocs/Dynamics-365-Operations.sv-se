--- 
title: "Skapa överföringsdokument för varurörelse inom ett företag"
description: "I den här proceduren visas hur du skapar överföringsdokument för varurörelser i ett företag."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: db6babb4cc679d8f3c6346e72013157a34ea3216
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-the-transfer-documents-for-goods-movement-inside-a-company"></a>Skapa överföringsdokument för varurörelse inom ett företag

[!include[task guide banner](../../includes/task-guide-banner.md)]

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

