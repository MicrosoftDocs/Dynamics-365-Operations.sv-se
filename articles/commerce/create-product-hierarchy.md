---
title: Skapa en ny produkthierarki
description: I det här avsnittet beskrivs hur du skapar en ny produkthierarki i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c7d0c792a8590be474b05dea262ae11d15e0ada3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965231"
---
# <a name="create-a-new-product-hierarchy"></a>Skapa en ny produkthierarki


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en ny produkthierarki i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Dynamics 365 Commerce stöder flera butikskanaler. Dessa kanaler inkluderar onlinebutiker, kundtjänst och butiker (kallas också fysiska butiker). Varje butikskanal kan ha egna betalsätt, prisgrupper, kassaregister (POS), intäkts- och utgiftskonton och personal. Du måste ställa in alla dessa element innan du kan skapa en butikskanel. 

En produkthierarki för Commerce används för att definiera den allmänna produkthierarkin för din organisation. Du kan använda en produkthierarki för Commerce för marknadsföring, prissättning och kampanjer, rapportering och sortimentplanering. Endast en produkthierarki för Commerce tilldelas per organisation.

## <a name="create-and-configure-a-product-hierarchy"></a>Skapa och konfigurera en produkthierarki

Följ stegen nedan om du vill skapa och konfigurera en produkthierarki för Commerce.

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> produkthierarki för Commerce**.
1. Om det inte finns någon hierarki ännu, i **åtgärdsfönstret**, välj **ny** för att skapa roten för hierarkin.
1. Under **allmänt**:
    1. Ange sedan ett namn i rutan **Namn**.
    1. Ange en beskrivning i rutan **beskrivning**.
    1. I rutan **Eget namn** anger du ett eget namn.
    1. Ange **Aktiv** till **Ja**.

## <a name="add-hierarchy-nodes"></a>Lägg till hierarkinoder

Gör så här för att lägga till hierarkinoder.

1. I åtgärdsfönstret klickar du på **Redigera kategorihierarki**.
1. Markera den överordnade nod som du vill lägga till en ny nod i och välj sedan **Ny kategorinod**.
1. I avsnittet **allmänt** finns **namn**, **beskrivning**, **eget namn** och **nyckelord**.
1. Under **allmänt**:
    1. Ange sedan ett namn i rutan **Namn**.
    1. Ange en beskrivning i rutan **beskrivning**.
    1. I rutan **Eget namn** anger du ett eget namn.
    1. I rutan **nyckelord**, ange relevanta nyckelord.
    1. I rutan **Visningsordning**, ange ett nummer för visningsordningen (valfritt).
1. Klicka på **Spara** i åtgärdsfönstret.
1. Upprepa stegen ovan om du vill lägga till fler noder.

Följande bild visar skapandet av en ny produkthierarkinod.

![Skapa en produkthierarki](media/create-product-hierarchy.png)

## <a name="other-settings"></a>Andra inställningar

Grupper av kategoriattribut kan också tilldelas till varje grupp efter behov.  

## <a name="additional-resources"></a>Ytterligare resurser

[Commerce-hierarkier](retail-hierarchies.md)

[Hantera produktkategorier och produkter](category-management-product-creation.md)

[Ändra sorteringsordning för marknadsföringsentiteter](custom-order-categories-nav-retail-prod-hierarchy.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]