---
title: Använd inställningar för måttenhet
description: Det här avsnittet behandlar inställningar för måttenhet och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d338ba207c9a101f5e224ca66555b16a457bcbc
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271411"
---
# <a name="apply-unit-of-measure-settings"></a>Använd inställningar för måttenhet

[!include [banner](includes/banner.md)]

Det här avsnittet behandlar inställningar för måttenhet och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.

En produkt kan säljas i olika enheter, till exempel "varje", "par" och "dussin". I Commerce-administrationen kan måttenheten för försäljning definieras för en produkt och visas på en näthandelsplats. Om till exempel en återförsäljare säljer en produkt både enskilt och per dussin kan de tillgängliga måttenheterna visas tillsammans med annan produktinformation.

I exemplet i följande illustration har måttenheten **ea** (varje) för försäljning angetts för en produkt i Commerce-administrationen.

![Exempel på en produkt som konfigurerats med en måttenhet i Commerce-administrationen](./media/Productunit-headquarters.PNG)

> [!NOTE]
> Stöd för att tillämpa och visa måttenheten är tillgängligt i version 10.0.19 av Commerce.

## <a name="unit-of-measure-settings"></a>Inställningar för måttenhet

Visningsinställningarna för måttenheten definieras i Commerce-webbplatsbyggaren på **Webbplatsinställningar: \> Tillägg \> Visa måttenhet för produkter**. Det finns tre inställningar som stöds:

- **Visa inte** – När den här inställningen har valts visar näthandelsplatsen inte produktens måttenhet. Detta beteende är standard.
- **Visa i produktens inköpsupplevelse** – När den här inställningen har valts visas måttenheten i produktinformation, kundvagn, kassa, orderhistorik och orderinformationssidor.
- **Visa i produktsöknings- och inköpsupplevelsen** – När den här inställningen har valts visas måttenheten på sidorna för produktköp och även i samband med sökupplevelsen för produkten. Som en del av detta beteende visas måttenheter i sökresultat och moduler för produktsamling.

> [!IMPORTANT]
> Visningsinställningar för måttenhet är tillgängliga från och med version 10.0.19 av Commerce. Om du uppdaterar från en äldre version av Commerce måste du uppdatera filen appsettings.json manuellt. För instruktioner, se [SDK- och modulbiblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-unit-of-measure-settings"></a>Moduler som använder inställningar för måttenhet

Moduler som använder måttenhetens inställningar inkluderar köprutan, listan, kundvagnen, kundvagnsikonen, sökresultatbehållare, produktsamling, kassa ut och moduler för orderinformation.

I exemplet i följande illustration visar en produktinformationssida (PDP) måttenheten (**ea**) för en produkt.

![Exempel på en PDP som visar måttenheten](./media/Productunit-PDP.png)

I exemplet i följande illustration visar en produktsamlingsmodul måttenheten (**ea**) för en produkt.

![Exempel på en produktsamlingsmodul som visar måttenheten](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Kundvagnsmodul](add-cart-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Sidor och moduler för kontohantering](account-management.md)

[Uppdateringar av SDK och modulbibliotek](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
