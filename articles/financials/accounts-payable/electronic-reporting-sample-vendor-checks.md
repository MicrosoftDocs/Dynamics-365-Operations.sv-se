---
title: "Elektronisk rapportering för provleverantörscheckar"
description: "Det här avsnittet innehåller allmän information om hur du använder provcheckformat för elektronisk rapportering."
author: twheeloc
manager: AnnBe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.assetid: 
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c9abea228cdaae84ca2b9aada9f36bbe79c1dc6b
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

[!include[banner](../includes/banner.md)]

# <a name="electronic-reporting-sample-check-formats"></a>Elektronisk rapportering för provcheckformat

Du kan använda elektronisk rapportering (ER) för att formatera leverantörens checkar. Det finns många bankspecifika och checkproviderspecifika checkformat på marknaden. Provcheckformat har inkluderats i betalningscheckmodellen i databasen för ER. Dessa provcheckar betecknas **check i mitten (USA)** och **check på övre stump under (USA)**.

## <a name="what-check-formats-are-currently-supported"></a>Vilka checkformat stöds för närvarande?

Du bör alltid gå till det delade resursbiblioteket i Microsoft Dynamics Lifecycle Services (LCS) och visa en lista över tillgängliga filer som har tillgångstypen **GER-konfiguration**. Nästa avsnitt "Vad måste jag ställa in?" innehåller en länk till ett hjälpavsnitt som beskriver hur du skapar en LCS-databas för att granska tillgängliga konfigurationer och importera valda konfigurationer.

Microsoft Dynamics 365 for Finance and Operations, Enterprise edition innehåller ett provformat där checken ligger överst, följt av två remitteringssektioner. Den innehåller också ett provformat där checken är i mitten mellan två remitteringssektioner. Dessa provformat motsvarar Deluxe affärscheckformat.

## <a name="what-do-i-have-to-set-up"></a>Vad måste jag ställa in?

- Innan du skriver ut checkar med ER måste minst en aktiv checkkonfiguration importeras till dina ER-konfigurationer. Instruktioner finns i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)
- När du konfigurerar kontanter och bankhanteringscheckar för bankkontot, markerar du kryssrutan **allmänna elektroniska exportformat** och väljer sedan lämpligt checkformat som en exportformatkonfiguration.
- Du måste också ange antalet följesedelsrader som ska skrivas ut på remitteringen. Kom ihåg att inkludera rubrikraderna när du beräknar denna siffra. För de två provcheckformaten är det rekommenderade antalet följesedelsrader 17. Men detta antal varierar beroende på checklagret och skrivardrivrutinerna.
- Vi rekommenderar att du skriver ut en testcheck för att validera checklayouten. Om du vill skriva ut en testcheck väljer du alternativ **Skriv ut test**. Testcheckformaten fungerar bäst när **marginaler** anges till **ingen** i skrivarens avancerade egenskaper för Microsoft Excel. När test checken har genererats aktiverar du redigering av Excel-utdata och konfigurerar sidans layout så att alla marginaler är **0** (noll). Jämför testkopian av checklagret och justera inställningarna tills du är nöjd med justeringen.
- När du genererar betalningar för det konfigurerade bankkontot i betalningsjournalen skrivs checkarna ut med det angivna formatet.

Mer information finns i [Ändra elektroniskt rapportformat](../../dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template.md).

