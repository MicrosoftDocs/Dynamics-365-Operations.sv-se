---
title: Serviceobjekt – översikt
description: Denna artikel innehåller en översikt över hur du arbetar med serviceobjekt.
author: sorenva
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8150a94677fe38f4caa6f3e0b5fb5d1be5972eaf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862423"
---
# <a name="service-objects-overview"></a>Serviceobjekt – översikt

[!include [banner](../includes/banner.md)]

Serviceobjekt är en kunds tillgångar och produkter som du kan utföra en tjänst för. Beroende på vilken typ av service du tillhandahåller kan objekt vara materiella eller immateriella:

-  Materiella objekt är saker, till exempel en maskin eller byggnad, som du kan utföra en fysisk serviceuppgift på.

    Ett materiellt serviceobjekt kan också vara en lagerartikel som du skapar i formuläret för information om frisläppt produkt. Beroende på den lagerdimensionsgrupp som du kopplar till artikeln kan du skapa ett serviceobjekt till en detaljnivån som visar artikelns serienummer. Detta är användbart när du måste hålla reda på exakt vilken artikel som serviceobjektet representerar.

    Ett materiellt serviceobjekt kan också vara en artikel som inte är direkt relaterad till företagets direkta tillverkning eller leveranskedja. Ett verktygskit som till exempel används för reparation i en serviceorder kan vara ett serviceobjekt som inte finns i lager. I det här fallet registrerar du det inte som en lagerartikel.

-  Immateriella objekt är icke fysiska ting, till exempel en grupp konton eller juridiska dokument, som du kan utföra serviceuppgifter på.

## <a name="example-of-an-intangible-service-object"></a>Exempel på ett immateriellt serviceobjekt

Företag A hanterar ekonomiska poster för flera mindre företag. En av företag A:s kunder är det lokala fotbollslaget, för vilket företag A sköter veckobokföringen den årliga granskningen av klubbens konton. Klubbens konton ställs in i formuläret serviceobjekt och specificeras som objektet i serviceavtalet. Det finns två rader för serviceavtal för objektet. Rad 1 är veckobokföring med ett veckointervall som tilldelats raden, och rad 2 är den årliga granskningen med ett årligt intervall som tilldelats den.

## <a name="related-articles"></a>Relaterade artiklar

[Skapa serviceobjekt](create-service-objects.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]