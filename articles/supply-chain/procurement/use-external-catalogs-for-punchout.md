---
title: Använd externa kataloger för PunchOut eProcurement
description: Denna artikel beskriver hur du kan använda externa kataloger för att skapa och skicka rekvisitioner.
author: GalynaFedorova
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchVendorPortalRequests, CatExternalCatalogBasketWizard, CatExternalCatalogPunchoutDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b3ef0a144cd1a893f08c73c3b00fa3cf6ae8f7bc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851693"
---
# <a name="use-external-catalogs-for-punchout-e-procurement"></a>Använd externa kataloger för PunchOut eProcurement

[!include [banner](../includes/banner.md)]

Genom att använda externa kataloger för PunchOut eProcurement behöver du inte underhålla information om dina leverantörers produkter i dina egna huvuddata. I stället konverteras shoppingvagnen på en leverantörs webbplats till rekvisitionsrader som har rätt produktinformation. 

Undvik att underhålla beskrivningar och priser på dina leverantörers produkter i dina egna huvuddata för produkten. Använd i stället externa kataloger för PunchOut eProcurement. När medarbetare sedan skapar rekvisitioner kan de ”omdirigeras” till en extern katalogwebbplats för en leverantör (d.v.s. de lämnar ditt system och går till leverantörens webbplats). Produkter som läggs till i shoppingvagnen på leverantörens webbplats kan sedan att konverteras till rekvisitionsrader. Därför får du rätt produktinformation: produkt-ID, namn, pris och så vidare.

Om du vill använda externa kataloger måste du skapa en rekvisition på sidan **Mina inköpsrekvisitioner**.

Den medarbetare som skapar en rekvisition kallas för förberedaren av rekvisitionen. Som förberedare kan du utföra följande uppgifter:

Använd radåtgärden **Externa kataloger** för att öppna en sida som innehåller alla externa kataloger som är tillgängliga för angivna beställaren, juridisk person för inköp och mottagande driftenhet.

Beroende på dina behörigheter, ändra beställaren, den juridiska personen för inköp och den mottagande driftenheten. En ändring av dessa värden kan ändra listan över externa kataloger som är tillgängliga för en beställare. Vilka externa kataloger som är tillgängliga beror på de aktuella aktiva inköpspolicyerna för den juridiska personen för inköp och den mottagande driftenheten. Dessa policyer kan tillåta eller neka åtkomst till specifika anskaffningskategorier. Därför kan listan över externa kataloger som är mappade till dessa anskaffningskategorier påverkas.

Mer information om hur du konfigurerar policyer finns i [Inköpspolicyer - översikt](../procurement/purchase-policies.md).

- Mata in text i katalogens sökfält om du vill söka efter externa kataloger för specifika anskaffningskategorier.
- Klicka på den externa katalogen om du vill lägga till produkter från en leverantörs extern katalog på leverantörens webbplats. Lägg sedan till produkter i shoppingvagnen och checka ut. Shoppingvagnsraderna överförs till Microsoft Dynamics 365.

Om det finns flera alternativ för anskaffningskategorier, markera rätt anskaffningskategori innan du lägger till rader i rekvisitionen.
När rader har lagts till i en inköpsrekvisition kan du lägga till fler rader utan att använda externa kataloger. Alternativt kan du fortsätta att använda externa kataloger för att lägga till rader.

När rekvisitionen är klar använder du åtgärden **Srbetsflöde** > **Skicka** för att skicka den för godkännande.

### <a name="additional-resources"></a>Ytterligare resurser

- [Ställ in en extern katalog för PunchOut eProcurement](set-up-external-catalog-for-punchout.md)
- [Förbättringar i inköps-cXML](purchasing-cxml-enhancements.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]