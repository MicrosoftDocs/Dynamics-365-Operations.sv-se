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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bcb78158afbf7bb0e9b83b35e37b1532a7c6283
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138194"
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

