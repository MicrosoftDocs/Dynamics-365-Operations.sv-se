---
title: Föreslå förvärv av anläggningstillgång
description: Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0997af638c141661afb677e2407a90a883168aed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447863"
---
# <a name="propose-fixed-asset-acquisitions"></a>Föreslå förvärv av anläggningstillgång

[!include [banner](../../includes/banner.md)]

Detta avsnitt beskriver hur du anskaffar en anläggningstillgång med hjälp av anskaffningsförslaget i anläggningstillgångsjournalen. Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen. Om du vill skaffa en anläggningstillgång via en förslagsjournal för anläggningstillgångar måste du först skapa anläggningstillgångsposten och sedan definiera anskaffningspriset i tillgångsförteckningen.

1. I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar**.
2. Välj **Ny**.
3. I fältet **Namn** anger eller väljer du ett värde.
4. Klicka på **Rader** i åtgärdsfönstret.
5. Välj **Förslag**.
6. Välj **Anskaffningsförslag**.
7. Välj **filter**. Välj **Återställ** för att rensa tidigare värden.
8. Välj raden med **numret på anläggningstillgången**.
9. I fältet **Kriterier** anger du eller väljer ett värde. Ange återstående kriterier för de anläggningstillgångar som du vill anskaffa med detta förslag.  
10. Välj **OK** två gånger för att avsluta fönstret.
- Kontrollera de skapade transaktionsraderna.  
- Endast anläggningstillgångar med anskaffningsdatum och anskaffningspris på räkenskapsboken inkluderas i anskaffningsförslaget.  
11. På sidan väljer du fliken **Böcker**.
12. Vald **bokföring**


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]