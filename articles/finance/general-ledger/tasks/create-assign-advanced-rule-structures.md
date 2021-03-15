---
title: Skapa och tilldela avancerade regelstrukturer
description: I det här avsnittet beskrivs hur du skapar och tilldelar en avancerad regelstruktur till en kontostruktur.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e6a3f7d174c91e357dce8a19ab50a5cd42a85561
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968620"
---
# <a name="create-and-assign-advanced-rule-structures"></a>Skapa och tilldela avancerade regelstrukturer

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du skapar och tilldelar en avancerad regelstruktur till en kontostruktur. Den här guiden använder demoföretaget USMF.

## <a name="create-an-advanced-rule-structure"></a>Skapa en avancerad regelstruktur
1. Gå till **Navigeringsfönster > Moduler > General ledger > Chart of accounts > Structures > Advanced rule structures**.
2. Välj **Nytt** om du vill öppna dialogrutan.
3. Ange ett namn som beskriver regelstrukturen i fältet **Avancerad regelstruktur**.
4. Välj **OK**.
5. Välj **Lägg till segment**.
6. Välj en ekonomisk dimension i listan med segment. Till exempel **Butik**.  
7. Välj **Lägg till segment**.
8. Välj **aktivera**.

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>Använd en avancerad regelstruktur för en kontostruktur
1. Gå till **Navigeringsfönster > Moduler > General ledger > Chart of accounts > Structures > Konfigurera kontostrukturer**.
2. I listan letar du upp och väljer den kontostruktur som du vill tillämpa den avancerade regeln på.
3. Välj **Redigera**. Du kan också klicka på **Avancerade regler** så uppmanas du att placera kontostrukturen i **utkastläge**.  
4. Visa **avancerade regler**.
5. Välj **Nytt** om du vill öppna dialogrutan.
6. Ange ett värde i fältet **Avancerad regel**.
7. Skriv ett värde i fältet **Namn**.
8. Markera **Skapa**.
9. Välj **Lägg till nya kriterier**.
10. Välj huvudkonto eller en ekonomisk dimension i fältet **Där**.
11. Välj ett alternativ i fältet **Operator**, t.ex. **är mellan** och **inkluderar**.
12. Ange ett värde i fältet **Värde**.
13. Skriv ett värde i fältet **via**.
14. Välj **Lägg till** för att öppna dialogrutan.
15. I listan letar du upp den avancerade regelstruktur som du vill använda när de villkor som du angett uppfylls.
16. Markera **Lägg till**.
17. Stäng sidan.
18. Välj **aktivera**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]