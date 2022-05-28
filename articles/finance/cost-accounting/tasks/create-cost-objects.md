---
title: 'Skapa kostnadsobjekt  '
description: I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för -kostnadsställen till kostnadsredovisning via en datakoppling.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 88196ea19488cd8572bf0e7883298317c9c84696
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734142"
---
# <a name="create-cost-objects"></a>Skapa kostnadsobjekt   

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för -kostnadsställen till kostnadsredovisning via en datakoppling. Demonstrationsdataföretaget USMF har använts för att skapa denna procedur. 


## <a name="create-new-cost-objects"></a>Skapa nya kostnadsobjekt
1. Gå till **Kostnadsredovisning > Dimensioner > Kostnadsobjektdimensioner**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Namn**.
4. Ange eller välj ett värde i fältet **Datakoppling för dimensionsmedlemmar**.
5. I fältet **Beskrivning** anger du ett värde.
6. Klicka på **Spara**.

## <a name="configure-the-data-connector"></a>Konfigurera datakopplingen
1. Klicka på **Konfigurera dimensionsmedlemsprovider**.
    * Välj CostCenter för att importera CostCenter-dimensionen till kostnadsredovisningen.  
2. Välj Kostnadscenter i fältet **Dimensionsnamn**.
3. Klicka på **OK**.

## <a name="import-cost-centers"></a>Importera kostnadsställen
1. Klicka på **Importera dimensionsmedlemmar**.
2. Klicka på **OK**.

## <a name="view-the-imported-cost-centers"></a>Visa de importerade kostnadsställena
1. Klicka på **Visa dimensionsmedlemmar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
