---
title: Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell
description: I den här proceduren visas hur du kan lägga till ett nytt begränsningsuttryck i en modell för produktkonfiguration.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77e8b991a2615a8f5d238acc4655f231edb6ca98
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569659"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Lägg till en uttrycksbegränsning i en produktkonfigurationsmodell

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du kan lägga till ett nytt begränsningsuttryck i en modell för produktkonfiguration. Här visas hur du kan bestämma att hörnskyddet måste användas på en högtalare om användaren har valt ett frontgaller i metall. Proceduren använder högtalarkomponenten i demonstrationsföretaget USMF.

## <a name="create-an-expression-constraint"></a>Skapa en uttrycksbegränsning

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
3. Hitta och markera önskad post i listan.
    * I det här exemplet används den avancerade högtalarmodellen.  
4. Klicka på länken på önskad rad i valda listan.
5. Visa avsnittet **Begränsningar**.
6. Markera **Lägg till**.
7. Markera **Skapa**.
8. Skriv ett värde i fältet **Namn**.

## <a name="enter-expression"></a>Skriv uttryck

1. Välj **Redigera uttryck**.
    * Om du låser upp användargränssnittet i uppgiften som registrerar i detta skede, kan du använda IntelliSense och listan över symboler för att skapa begränsningsuttrycket.  
2. I fältet **ConstraintBody** anger du "Implies[FrontGrill=="Metal", CornerProtection]" (utan citattecken före och efter).
    * Uttryckslogiken betyder: om frontgallret är av metall, måste hörnskyddsalternativet markeras.  
3. Välj **validera**.
    * Verifierafunktionen körs igenom begränsningsuttrycket och söker efter syntaxfel.  
4. Välj **Nära**.
5. Välj **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]