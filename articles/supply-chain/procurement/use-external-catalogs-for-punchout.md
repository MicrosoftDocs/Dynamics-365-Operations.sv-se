---
title: "Använd externa kataloger för PunchOut eProcurement"
description: "Det här avsnittet beskriver hur du kan använda externa kataloger för att skapa och skicka rekvisitioner."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c345f1f8d1aaa93dbe02f1f8c53df63bf3488a9e
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="use-external-catalogs-for-punchout-eprocurement"></a>Använd externa kataloger för PunchOut eProcurement
Genom att använda externa kataloger för PunchOut eProcurement behöver du inte underhålla information om dina leverantörers produkter i dina egna huvuddata. I stället konverteras shoppingvagnen på en leverantörs webbplats till rekvisitionsrader som har rätt produktinformation. 

Undvik att underhålla beskrivningar och priser på dina leverantörers produkter i dina egna huvuddata för produkten. Använd i stället externa kataloger för PunchOut eProcurement. När medarbetare sedan skapar rekvisitioner kan de ”omdirigeras” till en extern katalogwebbplats för en leverantör (d.v.s. de lämnar ditt system och går till leverantörens webbplats). Produkter som läggs till i shoppingvagnen på leverantörens webbplats kan sedan att konverteras till rekvisitionsrader. Därför får du rätt produktinformation: produkt-ID, namn, pris och så vidare.

Om du vill använda externa kataloger måste du skapa en rekvisition på sidan **Mina inköpsrekvisitioner**.

Den medarbetare som skapar en rekvisition kallas för förberedaren av rekvisitionen. Som förberedare kan du utföra följande uppgifter:

Använd radåtgärden **Externa kataloger** för att öppna en sida som innehåller alla externa kataloger som är tillgängliga för angivna beställaren, juridisk person för inköp och mottagande driftenhet.

Beroende på dina behörigheter, ändra beställaren, den juridiska personen för inköp och den mottagande driftenheten. En ändring av dessa värden kan ändra listan över externa kataloger som är tillgängliga för en beställare. Vilka externa kataloger som är tillgängliga beror på de aktuella aktiva inköpspolicyerna för den juridiska personen för inköp och den mottagande driftenheten. Dessa policyer kan tillåta eller neka åtkomst till specifika anskaffningskategorier. Därför kan listan över externa kataloger som är mappade till dessa anskaffningskategorier påverkas.

Mer information om hur du ställer in policyer finns i [Inköpspolicyer](../procurement/purchase-policies.md).

- Mata in text i katalogens sökfält om du vill söka efter externa kataloger för specifika anskaffningskategorier.
- Klicka på den externa katalogen om du vill lägga till produkter från en leverantörs extern katalog på leverantörens webbplats. Lägg sedan till produkter i shoppingvagnen och checka ut. Shoppingvagnsraderna överförs till Microsoft Dynamics 365.

Om det finns flera alternativ för anskaffningskategorier, markera rätt anskaffningskategori innan du lägger till rader i rekvisitionen.
När rader har lagts till i en inköpsrekvisition kan du lägga till fler rader utan att använda externa kataloger. Alternativt kan du fortsätta att använda externa kataloger för att lägga till rader.

När rekvisitionen är klar använder du åtgärden **Srbetsflöde** > **Skicka** för att skicka den för godkännande.

