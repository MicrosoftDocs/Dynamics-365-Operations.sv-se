---
title: Välja ett tema för webbplatsen
description: I denna artikel beskrivs hur du konfigurerar eller ändrar webbplatstemat i Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b038dc996c571d54dce3f2aec679f7af8af85074
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900396"
---
# <a name="select-a-site-theme"></a>Välja ett tema för webbplatsen

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar eller ändrar webbplatstemat i Microsoft Dynamics 365 Commerce.

En webbplats layout och stil (t.ex. teckensnitt, storlekar och färger) definieras av det tema som du väljer och tillämpar på webbplatsen. Ett tema skapas och distribueras av en utvecklare på ditt företag. En översikt över teman finns i [Översikt över teman](e-commerce-extensibility/theming.md). Mer information om hur du skapar och distribuerar teman finns i [Skapa ett nytt tema](e-commerce-extensibility/create-theme.md).

När du först skapar en webbplats använder den som standard ett tema som heter **Fabrikam**. Det här standardtemat ingår i Commerce-modulbibliotek. När du har distribuerat ytterligare teman för platsen kan du konfigurera platsen så att den använder en av dem i stället.

## <a name="select-the-site-theme"></a>Välj ett tema för webbplatsen

Gör så här för att välja det tema som ska användas på webbplatsen:

1. I webbplatsens redigeringsmiljö, gå till din webbplats.
1. Gå till **Webbplatshantering** \> **Utbyggbarhet**.
1. Under **Tema**, välj ett tema i den nedrullningsbara menyn.
1. Om du vill använda det valda temat på webbplatsen väljer du **Spara och publicera**.

> [!NOTE]
> Temat som du väljer publiceras på din webbplats så snart du väljer **Spara och publicera** på sidan **Utbyggbarhet**. Om du vill förhandsgranska ett tema på din webbplats innan du använder det, kan du använda din utvecklings- eller begränsat läge-miljö.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägga till en logotyp](add-logo.md)

[Arbeta med CSS åsidosättningsfiler](css-override-files.md)

[Lägga till en favoritikon](add-favicon.md)

[Lägga till ett copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)

[Översikt över teman](e-commerce-extensibility/theming.md)

[Skapa ett nytt tema](e-commerce-extensibility/create-theme.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
