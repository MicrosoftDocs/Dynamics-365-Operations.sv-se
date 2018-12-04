---
title: "Skapa en artikelersättningsorder"
description: "Ersättningsorder skapas vanligtvis efter att en produkt har returnerats och inspekterats."
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1f0cd629658972f98e2233dfa287940c4444b82a
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="create-an-item-replacement-order"></a>Skapa en artikelersättningsorder 

[!include [banner](../includes/banner.md)]


Ersättningsorder skapas vanligtvis efter att en produkt har returnerats och inspekterats. Om en artikel måste ersättas innan den returneras eller om artikeln inte kommer att returneras kan du emellertid skapa en ersättningsorder omedelbart efter att du har skapat en returorder.

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a>Skapa en ersättningsorder efter att du har tagit emot en artikel som returneras

1.  Klicka på **Försäljning och marknadsföring** \> **Returorder** \> **Alla returorder** \> **Alla försäljningsorder**.

2.  Skapa en ny returorder eller välj en returnerad order i listan för att öppna formuläret **Returorder - RMA-nummer: %1, %2**.

3.  Klicka på **rad**, och välj sedan **ersättningsartikeln**.

4.  Välj artikeln som ska ersätta den returnerade artikeln med. Ange artikelspecifikationerna och klicka sedan på **Verkställ**.

5.  Klicka på **Följesedel** för att generera följesedeln för returordern. En försäljningsorder skapas för ersättningsartikeln du har valt.
    
    Efter att försäljningsordern har skapats för ersättningsartikeln, försäljningsavtal söks automatiskt och, om det finns en lämplig försäljningsavtal, används den till försäljningsordern.

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a>Skapa en ersättningsorder, innan du tar emot en artikel som ska returneras

1.  Klicka på **Försäljning och marknadsföring** \> **Returorder** \> **Alla returorder** \> **Alla försäljningsorder**.

2.  Skapa en ny returorder eller välj en returorder i listan för att öppna formuläret **Returorder - RMA-nummer: %1, %2**.

3.  Klicka på **Hitta försäljningsorder** om du vill identifiera försäljningsordern för den returnerade artikeln. Slutför formuläret **söka efter försäljningsorder** och klicka på **OK** för att stänga formuläret och återgå till formuläret **returorder - RMA-nummer: %1, %2**. Försäljningsorderraden för den returnerade artikeln kopieras till returordern.

4.  Klicka på **Ersättningsorder** för att öppna formuläret **Skapa försäljningsorder**.

5.  Markera kryssrutan **Kopiera returorderrader** ör att överföra detaljer från den returorder som du markerade på formuläret **Returorder - RMA-nummer: %1, %2** till den här försäljningsordern.

6.  Ange eller ändra detaljer vid behov.
    
    Om du identifierar försäljningsordern i steg 3 och om försäljningsorderraden för returnerade artikeln är kopplad till en försäljningsavtal, kommer identifieraren för den tillämpliga försäljningsavtalet för artikelutbytesordern automatiskt visas i fältet**Försäljningsavtals-ID**.

7.  Klicka på **OK** för att stänga **Skapa försäljningsorder** och öppna formuläret **Försäljningsorder** där du kan fortsätta att ange information för den nya försäljningsordern. Vissa tillämpliga returorderrader ska kopieras till den nya försäljningsordern. 
    
    Om identifieraren för försäljningsavtalet visas automatiskt i fältet **Försäljningsavtals-ID** har försäljningsavtalet länkats till försäljningsorderrubriken för artikelutbytesordern. Om det finns en lämplig åtagande i försäljningsavtalet som ännu inte har fullgjorts, och försäljningsorder skapas före försäljningsavtalet går ut, skapas en koppling mellan försäljningsavtalraden och försäljningsorderraden. Därför information kopieras från försäljningsavtalet, till exempel artikelpris, till den nya försäljningsorderraden. 
  



