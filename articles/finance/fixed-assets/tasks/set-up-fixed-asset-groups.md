---
title: Ställ in anläggningstillgångsgrupper
description: I det här avsnittet förklaras hur du skapar en ny anläggningstillgångsgrupp.
author: saraschi2
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4eead36e1274194b151b230767a4d6385173b12f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994850"
---
# <a name="set-up-fixed-asset-groups"></a>Ställ in anläggningstillgångsgrupper

[!include [banner](../../includes/banner.md)]

I det här avsnittet förklaras hur du skapar en ny anläggningstillgångsgrupp. Här används revisorrollen och demonstrationdata för den juridiska personen USMF.

1. I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Inställningar > Anläggningstillgångsgrupper**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Anläggningstillgångsgrupp**.
4. Skriv ett värde i fältet **Namn**. Autonummer för anläggningstillgångar och nummerseriekoden i **anläggningstillgångsgruppen** ska åsidosätta inställningarna i anläggningstillgångparametrarna. Du kan ändra här, om tillgången i denna anläggningstillgångsgrupp ska ha ett nummer från andra grupper.  
5. Välj **Räkenskapsböcker**.
6. Ange eller välj ett värde i fältet **Bok**. Fältet **Beräkna avskrivning** är inställt på **Ja**, varför tillgångsförteckningen kommer att tas med i avskrivningsförslagen. Om **Beräkna avskrivning** är **Nej**, skrivs tillgången inte automatiskt av.  
7. Ange tillgångens tjänstelivstid, i antal år. Värdet i fältet **Avskrivningsperioder** beräknas efter att du har angett tjänstelivstid.  
8. Välj alternativ i fältet **Avskrivningspraxis**.
9. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]